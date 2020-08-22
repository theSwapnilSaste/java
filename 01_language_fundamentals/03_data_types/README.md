# 1.03 Data Types

1. In Java every variable and very expression in Java has some type.
2. Each and every data type is clearly defined.
3. Each and every assignment should be checked by complier for type-compatibility.

    | Expression | Java | C Language |
    |---|:--:|:--:|
    |`int x = 10.5 ;`|![Invalid](https://img.shields.io/badge/Valid%3F-No-red)|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
    |`boolean b = 0 ;`|![Invalid](https://img.shields.io/badge/Valid%3F-No-red)|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|

---

## Object Oriented Analogy

1. When compared with old languages, Java has Object-Oriented nature
2. If considered Java alone, Java lacks many OOP features like `operator-overloading, multiple-inheritance`

Q. Is Java purely object oriented programming language?
**NO** Java is not considered as pure object oriented programming language because several OOPs features are not satisfied by Java. (Like Operator Overloading, Multiple Inheritance). Moreover, we are depending on Primitive Data Types which are non-objects.

---

## Primitive Data Types (8)

Primitive Data Types are further divided into:

1. Numeric Data Types
    1. Integral Data Types
        * byte
        * short
        * int
        * long
    2. Floating Point Data Types
        * float
        * double
2. Non-Numeric Data Types
    * char
    * boolean

**NOTE** 01

1. String is non-primitive because only class can have methods. Primitive can not. And String need many functions to be called upon while processing like substring, indexof, equals, touppercase. It would not have been possible without making it class.\
Also class has made it possible to make strings immutable and final to enhance security and efficiency by allowing pooling.
2. Except `boolean` and `char` all other primitive data types are considered as signed data types. because we can represent both positive and negative numbers.

---

### byte

|MSB|   |   |   |   |   |   |   |
|:-:|---|---|---|---|---|---|---|
| X | 1 | 1 | 1 | 1 | 1 | 1 | 1 |

* size: 8 bits
* signed data type
* max value: `127`
* min value: `-128`
* MSB( Most Significant Bit ) acts as signed bit,
  * 0 means Non-negative number.
  * 1 means negative number.
* Positive number will be represented directly in the memory, while negative numbers are represented in the form of 2's compliments

#### TEST 01

Q. Which of the following are **valid** in Java?

|Sr. No | Example | Output |
|---|---|---|
| 1.| byte b = 10; |![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 2.| byte b = 127;|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 3.| byte b = 128;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Possible loss of Precision**: <br/> found: int required: byte|
| 4.| byte b = 10.5;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Possible loss of Precision**: <br/>found: double required: byte|
| 5.| byte b = true;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types**: <br/>found: boolean required: byte|
| 5.| byte b = "nana";|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types**: <br/>found: java.lang.String required: byte|

#### NOTE 02

If you want to handle data in form of strings (files or network etc.) best suitable form is `byte` because it is supported by both files and network.\
Example:

``` java
import java.io.FileOutputStream;  
public class FileOutputStreamExample {  
    public static void main(String args[]) {
           try{
             FileOutputStream fout=new FileOutputStream("D:\\testout.txt");
             String s="Welcome to DurgaSoft.";
             byte b[]=s.getBytes();//converting string into byte array
             fout.write(b);        //them writing it to the file via stream
             fout.close();
             System.out.println("success...");
            }
            catch(Exception e) {
              System.out.println(e);
            }
      }
}  
```

---

### short

* **Most Rarely used data type in Java**
* size: 8 bits
* signed data type
* max value: **2<sup>15</sup>-1** : `+ 32767`
* min value: **-2<sup>15</sup>**: `- 32768`
* Positive number will be represented directly in the memory, while negative numbers are represented in the form of 2's compliments

Q. Which of the following are **valid** in Java?

|Sr. No | Example | Output |
|---|---|---|
| 1.| short s = 32767;|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 2.| short s = 32768;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Possible loss of Precision**:<br/>found: int required: short|
| 3.| short s = 10.5;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Possible loss of Precision**:<br/>found: double required: short|
| 4.| short s = true;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types**:<br/>found: boolean required: short|
| 5.| short s = "nana";|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types**:<br/>found: java.lang.String required: short|

Q. When is short data type the **best** choice?\
Java came in 1995, we had 8085, 8086 microprocessors. 16-bit processors were very popular at that time. Data was represented in 16 bit data type.\
Hence, as Expected and Provided form are same, **read and write** operations are more efficient. Hence short is outdated right now as these are not in use.

---

### int

* **Most commonly used data type in Java**
* size: 32 bits
* signed data type
* max value: **2<sup>31</sup>-1** : `+ 2147483647`
* min value: **-2<sup>31</sup>**: `- 2147483648`

Q. Which of the following are **valid** in Java?

|Sr. No | Example | Output |
|---|---|---|
| 1.| int x = 2147483647;|![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 2.| int x = 2147483648;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Integer number too large**|
| 3.| int x = 2147483648l;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Possible loss of Precision**:<br/>found: long required: int|
| 4.| int x = true;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types**:<br/>found: boolean required: int|

---

### long

* size: 8 bytes = 64 bits
* signed data type
* max value: **2<sup>63</sup>-1**
* min value: **-2<sup>63</sup>**

Sometimes `int` range may not be enough to hold big values. In such cases `long` data type should be used\
Example:

1. Amount of distance travelled by light in **1000 days.**
`long l = 1260006060l;`
2. The number of characters present in a big file may exceed int range. Hence, the return type of `length()` method is **long but not int**\
`long l = file.length();`

#### NOTE 03

All the above data types (byte, short, int, long) meant for representing Integral values. If we want to represent floating point values then we should go for floating point data types.

---

## Floating Point Data Types

There are 2 floating point data points

* float : smaller fractional accuracy (5-6 decimal places)
* double : smaller fractional accuracy (14-15 decimal places)

|float|double|
| :---| :--- |
| For precision up to 5-6 decimal places | For precision up to 14-15 decimal places |
| If we want 5 to 6 places of accuracy then we should go for float | If you want 14-15 decimal places of accuracy then we should go for double |
| Single Precision | Double Precision |
| float follows single precision|double follows double precision |
| size: **4 bytes**| size: **8 bytes** |
| **Range: -3.4e38 to 3.4e38** | Range: **-1.7e308 to 1.7e308** |

---

### boolean

* Size: **IN JAVA SIZE OF boolean NOT APPLICABLE!!** (Virtual Machine dependant)
* Range: Not Applicable but allowed values are **true, false**
`boolean b = true;`
`boolean b = 0;`

| Sr. No | Example | Output |
|---|---|---|
| 1.| boolean b = true; |![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)|
| 2.| boolean b = 0;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types**:<br/>found: int required: boolean|
| 3.| boolean b = True;|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Cannot find symbol**:<br/>variable:True location: class {className}|
| 2.| boolean b = "True";|![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types**:<br/>found: java.lang.String required: boolean|

``` java
class Test {
    public static void main(String[] args) {
        int x = 0;
        if(x) {
          System.out.println("Hello");
        }
        else {
          System.out.println("Hi");
        }
    }
}
```

![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types** - found: int required: boolean

``` java
class Test {
    public static void main(String[] args) {
        while(1) {
          System.out.println("Hi");
        }
    }
}
```

![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types** - found: int required: boolean

---

### char

> Old languages (like C, C++) are ASCII code based and number of different ASCII code characters are <= 256.\
To represent these 256 characters 8 bits are enough. Hence, the size of char in old languages is 1 byte\
But, Java is Unicode based and number of allowed characters are > 256 but <=65536\
to represent these many characters 8 bits may not be enough, compulsorily we should go for 16 bit.\
Hence, size of char in java is 2 bytes

| Old Languages (C,C++) - ASCII Based | Java - Unicode Based |
|---|---|
| Size: 1 byte | Size: **2 byte** |
| To represent 256 char, 8 bits are enough| 8 bits are not enough|
| `A-Z, a-z, 0-9, symbols` |  ASCII + many other characters |
|Range: 0 - 256 | 0 - 65535 |

---

## SUMMARY

| Data Type | Size | Range | Wrapper Class | Default Value |
|---|---|---|---|---|
| byte | 1 byte |  -2<sup>7</sup> to 2<sup>7</sup>-1    | Byte  | 0  |
| short | 2 bytes | -2<sup>15</sup> to 2<sup>15</sup>-1 | Short  | 0 |
| int | 4 bytes |  -2<sup>31</sup> to 2<sup>31</sup>-1  | Integer  | 0  |
| long | 8 bytes | -2<sup>63</sup> to 2<sup>63</sup>-1  | Long  | 0  |
| float | 4 bytes | -3.4e38 to 3.4e38                   | Float  | 0.0  |
| double | 8 bytes | -1.7e308 to 1.7e308                | Double  | 0.0  |
| boolean | N/A |   true, false                         | Boolean  |  false |
| char | 4 bytes |  0 to 65535                          | character  |  0(space) |

**Note** that `null` cannot be used for primitive data types. `null` is default value for **object** data type.

``` java
class Test {
    public static void main(String[] args) {
        char ch = null;
    }
}
```

![Invalid](https://img.shields.io/badge/Error-Compile%20Time-red) **Incompatible Data Types** - found: `<nulltype>` required: char

---

### Next Topic: [1.04 Literals](../04_literals/README.md)
