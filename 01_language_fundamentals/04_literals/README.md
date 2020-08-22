# 1.04 Literals

## Definition of Literals

Any constant value which can be assigned to a variable is called as a  Literal.

``` java
class Test {
    public static void main(String[] args) {
        int x = 10;
    }
}
```

## Integral Literals

For integral data types `(byte, short, int, long)` we can specify literal value in the following ways

### Decimal Form

A number by default **without any prefix / suffix** is treated as Decimal Form. Allowed degits are ` 0-9 `

``` java
class Test {
    public static void main(String[] args) {
        int x = 10;
    }
}
```

### Octal Form

If a number is **prefixed** with `'0'`, it is treated as **'octal form'**. Allowed digits are ` 0-7 `

``` java
class Test {
    public static void main(String[] args) {
        int x = 010; // Octal Form
    }
}
```

### Hexa Decimal Form

If a number is **prefixed** with `'0x'` or `' 0X '`, it is treated as **'octal form'**. Allowed digits are ` 0-9 , A-F(lower-case & upper-case), x `. For extra digits ` a-f ` we can use both Lower-Case and Upper-Case characteres. These is one of very few areas where Java is **not case-sensitive**.

``` java
class Test {
    public static void main(String[] args) {
        int x = 0x10; // Hexa Decimal Form.
        int y = 0X10; // Both upper & lower case are allowed.
        int z = oxAdf;// Same for the additional allowed characters.
    }
}
```

### Long Form

By default every Integral Literal is of ` int ` type, but we can explicitly as Long type by adding suffix `'l'` or `'L'`

``` java
class Test {
    public static void main(String[] args) {
        long l = 10L;
    }
}
```

![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)

``` java
class Test {
    public static void main(String[] args) {
        int z = 10L;
    }
}
```

![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Possible Loss of Pricision**

---

### Test - Integral Literals

Q. Which of the following declarations are **valid** in Java ?

|Sr. No. | Identifier | Answer |
|---|---|---|
| 1. |`int x = 10;`|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 2. |`int x = 0876;`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Integer Number too Large**|
| 3. |`int x = 0777;`|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 4. |`int x = oXFace`|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 5. |`int x = 0xBEEF`|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 6. |`int x = 0xBEER`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **';' Expectede**|

Q. In the following code identify **number of Identifiers** present and highlight them -

``` java
class Test {
    public static void main(String[] args) {
        int x = 10;
        int y = 010;   //  (010)8 = (8)10
        int z = 0x10; // (0x10)16 = (16)10

        System.out.println(x + " "+ y + " " + z)
    }
}
```

**NOTE**: Programmers have choice to specify value in Decimal, Octal, Hexadecimal form. But JVM will always provide value in only the **'Decimal Form'.**

---

### byte short Literals

There is no direct way to specify byte and short literals explicitly like `byte b = 10b or short s = 10s;`. But indirectly We can specify them.

Whenever we are assigning Integral literals to the byte/short variable and value is within the range of byte/short then compiler automatically treats it as byte/short literal.

``` java
class Test {
    public static void main(String[] args) {
        byte b = 10;  // within byte range
        byte b = 127; // within byte range
    }
}
```

![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)

``` java
class Test {
    public static void main(String[] args) {
        byte b = 128;
    }
}
```

![Invalid](https://img.shields.io/badge/Valid%3F-No-red) **Possible Loss of Precision**: Found: int Required: byte

``` java
class Test {
    public static void main(String[] args) {
        short s = 32768;
    }
}
```

![Invalid](https://img.shields.io/badge/Valid%3F-No-red) **Possible Loss of Precision**: Found: int Required: short

## Floating Point Literals

By default every floating point literal is of double type and hence we can't assign directly to the float variable. but we can specify floating point literal as float type by using suffix ` f ` or ` F `.
just like compiler considers Integral number as int type, it takes every floating point literal is double type.

``` java
class Test {
    public static void main(String[] args) {
        float f = 123.456;
    }
}
```

![Invalid](https://img.shields.io/badge/Valid%3F-No-red) **Possible Loss of Precision**: Found: double Required: float

``` java
class Test {
    public static void main(String[] args) {
        float f = 123.456f;
        double d = 123.345;
        double e = 123.456d; // we can use this, but not required
    }
}
```

![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)

We can specify explicitly floating point literal as double type but adding suffix `d` or `D`. Of course this convention is not required.

``` java
class Test {
    public static void main(String[] args) {
        double d = 123.456D; // we can use this, but not required
        double e = 123.456d; // we can use this, but not required
    }
}
```

![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)

### Test -Floating Point Literals

Q. Which of the following declarations are **valid** in Java ?

|Sr. No. | Expression | Answer |
|---|---|---|
| 1. |`double d = 123.456;`|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 2. |`double d = 023.456;`|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) **Treated as decimal only!!(not octal)**|
| 3. |`double d = 0x3.456;`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Malformed floating point literal**|

**Note that,** we can specify floating point literal only in decimal form and we can not specify in octal and hecdcimal forms. Even though octal declaration won't give any error, it is actually treated as decimal as it is.

``` java
class Test {
    public static void main(String[] args) {
        double d = 0123.456;   // here you might think it is octal
        System.out.println(d); // and will be converted and printed.
    }                          // but it will be used as decimal only.
}
```

**LOOPHOLE** YOU WILL FAIL IN FOLLOWING FOR SURE!

|Sr. No. | Expression | Answer |
|---|---|---|
| 1. |`double d = 0786;`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Integer Number too Large**|
| 2. |`double d = 0xFACE;`|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |

**Note** the following:

 `0786` and `0xFACE` aren't floating point literals.

 They are integral. In the previous rule we were talking about floating point literals being assigned to double, These are integral literals which can be directly assigned.

 but `0786` is an invalid octal number. Hence, first one is invalid and second one is valid!!

In short, we can assign integral literal directly to floating point variables and that integral literal can be specified either in decimal / octal / hexadecimal forms.

---

### TEST - Floating Pooint Literals

Q. Which of the following are **valid** Java identifiers?

![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)
![Invalid](https://img.shields.io/badge/Valid%3F-No-red)

|Sr. No. | Identifier | Answer |
|---|---|---|
| 1. | `double d = 0786`| ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Integer Number too Large** (8) |
| 2. | `double d = oxFACE`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) (64206.0)|
| 3. | `double d = 0786.0`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) treated as Decimal |
| 4. | `double d = 0xFACE.0`| ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Floating point literal can be decimal only.|
| 5. | `double d = 10`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) (converted to 10.0) |
| 6. | `double d = 0777`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) (converted to 777.0) |
| 7. | `double d = 10`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 8. | `int d = 10.0`| ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) |

> We can't assign floating point literals to integral types.

### TEST - Exponential form

|Sr. No. | Identifier | Answer |
|---|---|---|
| 1. | `double d = 1.2e3` |![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) converted to 1200.0 |  
| 2. | `float f = 1.2e3` | ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Possible Loss of Precision** |
| 3. | `float f = 1.2e3f` |![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) converted to 1200.0f |  

>We can specify floating point literal even in exponential form (Scienticc Notation). By  default it is treated as Double.
---

## boolean Literals

For boolean data type, only allowed values are `true, false`

|Sr. No. | Identifier | Answer |
|---|---|---|
| 1. |`boolean b = true`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 2. |`boolean b = 0`| ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Incompatible types. Found: int Required:boolean |
| 3. |`boolean b = True`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Cannot find symbol: Variable True|
| 4. |`boolean b = "true"`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Incompatible types. Found: java.lang.String Required:boolean |

``` java
class Test {
    public static void main(String[] args) {
        int x =0;

        if(x) {
            System.out.println("Prerana")
        }
        else {
            System.out.println("Prerana")
        }
}
```

![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Incompatible types. Found: int Required:boolean

``` java
class Test {
    public static void main(String[] args) {
        while(1) {
            System.out.println("Hello");
        }
}
```

![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Incompatible types. Found: int Required:boolean

---

## char Literals

**Method 1** We can specify charr literal as single character within **single quotes.**

``` java
char ch = 'a';
```

![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)

``` java
char ch = "a" ;
```

![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Incompatible types. Found: java.lang.String Required:boolean

``` java
char ch = a ;
```

![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) cannot found symbol: variable a. Location a;

``` java
char ch = 'ab' ;
```

1. ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Unclosed char literal. (because ' is expected after a)
2. ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Unclosed char literal. (because ' is expected before b)
3. ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Not a Java Statement.

**Method 2** We can also specify char literal as **Integral Literls** and that Integral literal can be specified either in decimal/octal/hexadecimal forms. but, the allowed range is `0-65535`

|Sr. No. | Identifier | Answer |
|---|---|---|
| 1. |`char ch = 97`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 2. |`char ch = 0xFACE`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 3. |`char ch = 0777`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 4. |`char ch = 65535`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 5. |`char ch = 65535`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Incompatible types. Found: int required: char |

**NOTE:** Sometimes we might get the `?` as the output, the reason is the corresponding symbol might not have been intalled in the system.

**Method 3** Unicode Representation - We can represent char literal in Unicode form : `char ch = '\uxxxx'` where xxxx is 4-digit hexa-decimal form.

``` java
class Test {
    public static void main(String[] args) {
        char ch = '\u00061';
            System.out.println(ch);
        }
}
```

![Output: a](https://img.shields.io/badge/Output-a-brightgreen)

Mathod 4 Every escape character is a valid char literal. In Java there are 8 valid escape characters.

|Sr. No.| Escape Char|Description|
|---|---|---|
| 1. | `\n` | New Line |
| 2. | `\t` | Horizontal Tab |
| 3. | `\r` | Carraige Return |
| 4. | `\b` | Back Space |
| 5. | `\f` | Form Feed |
| 6. | `\'` | Single Quote Symbol |
| 7. | `\"` | Double Quote Symbol |
| 8. | `\\` | Backslash Symbol |

![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)
![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Illigal Escape Character

### TEST - char Lierals

Q. Which of the following declarations are **valid** in Java ?

|Sr. No. | Identifier | Answer |
|----|---|---|
| 1. |`char ch = 54536;` |![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Found int|
| 2. |`char ch = 0xBEER;`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **';' Expectede**|
| 3. |`char ch = \uface;`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Quotes are Missing|
| 4. |`char ch = '\uface';`|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 5. |`char ch = '\m'`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Illigal Escape Character|
| 6. |`char ch = '\iface'`|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) Illigal Escape Character, multiple errors|

---

## String Literal

Any sequence of characters within double quotes is treated as **'String Literals'.**
Example: `String s = "Hello Trixy"`;

--

## Enhancements w.r.t. Literals in Versions

### V1.7 - Binary Literals

For integrals data types until 1.6 version we can specify literal value in three ways:

1. Decimal
2. Octal
3. HexaDecimal

but from `Version 1.7` we can specify it in **Binary Forms** also, allowed digits are `0 and 1`. Literal value should be prefixed with `0b or 0B`.

``` java
class Test {
    public static void main(String[] args) {
        int x = '0b1111';
            System.out.println(x);
        }
}
```

![Output: 15](https://img.shields.io/badge/Output-15-brightgreen)

### V1.7 - Usage of '_'(underscore) in numeric Literals

From `Version 1.7` we can use underscore symbol '_' between digits of numeric literals.

`double d = 1_23_345.7_8_9;`
`double d = 123_345.7_8_9;`

The main advantage of this approach is that the readability of the code will be improved.
>At the time of compilation these underscore symbols will be removed automatically. Hence after compilation the above lines will become `double d = 123456.789;`

We can use more than One underscore symbol also between the digits.
Hence, `double d = 123_____3__4___5.7_8_9;` is totally Valid.

Q. Which of the following declarations are **valid** in Java ?

|Sr. No. | Identifier | Answer |
|----|---|---|
| 1. | `double d =_1_23_456.789;` | ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red)|
| 2. | `double d =1_23.456_.789;` | ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red)|
| 3. | `double d =123__456.789_;` | ![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red)|

Error: Underscores have to be located within digits

>These underscores are allowed for readability, we can use underscore symbols between digits only. near the '.',at beginning, at end is not allowed; we'll get compile time error.

``` txt
 byte ---> short --                             |
1byte       2 byte  \                           |
                     \                          |
                      ----> int   ----> long ------> float ----> double
            char ___ /     4 byte       8 byte  |   4 byte       8 byte
           2 byte                               |
                    INTEGRAL LITERALS           |   FLOATING POINT LITERALS
```

**IMPORTANT:** `8 byte long` value we can assign to `4 byte float` variable because, both are following different memory representations internally.

``` java
class Test {
    public static void main(String[] args) {
        float x = 10L;
           System.out.println(x);
        }
}
```

![Output: 10.0](https://img.shields.io/badge/Output-10.0-brightgreen)

**IMPORTANT:** `2 byte short` value we can not assign to `2 byte char` variable and vice versa. because, one is signed and other is unsigned hence the range of the both is different.

### Next Topic: [1.05 Arrays](../05_arrays/README.md)
