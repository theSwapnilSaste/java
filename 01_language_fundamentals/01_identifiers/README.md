# 1.01 Identifiers

## Definition of Identifiers

***Identifier:*** A name in Java program is called Identifier, which can be used for identification purpose.\
It can be any of the following:

* Variable Name
* Class Name
* Label Name

Q. In the following code identify **number of Identifiers** present and highlight them -

``` java
class Test {
    public static void main(String[] args) {
        int x = 10;
    }
}
```

Identifiers:

* **Test** - class name
* **main** - method name
* **String** - predefined java class name
* **args** - name of array
* **x** - name of variable

Total 5 identifiers in above example

---

## Rules for defining Java identifiers

1. **Characters we can use:** The only allowed characters are-\
`a-z, A-Z, 0-9, '$', '_'`\
Examples:
    1. `total_Num` - ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)
    2. `totalNum#` - ![Invalid](https://img.shields.io/badge/Valid%3F-No-red)\
If we are using any other character we'll get compile time error.

2. **Identifier should mot start with digit** As the rule name suggest an Identifier can't start with digit.\
Examples:
    1. `total123` - ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)
    2. `123total` - ![Invalid](https://img.shields.io/badge/Valid%3F-No-red)\
If we are using any other character we'll get compile time error.

3. **Case-Sensitive:** Not just Identifiers, whole Java language is treated as Case-Sensitive programming language.
    Q. **Is following code valid?**

    ``` java
    class Test {
        public static void main(String[] args) {
            int number = 10;
            int Number = 20;
            int NUMBER = 30;
        }
    ```

    ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)

4. **Length Limit:** Even though there is no limit for java identifiers, it is not recommended to take too lengthy identifiers.
Examples:
    1. `int JavaSupportsReallyReallyLongLongIdentifier = 0;` - ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)

5. **We can't use reserved words as identifiers::** In Java we can't use reserved words as identifiers.
Examples:
    1. `int a = 10;` - ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)
    2. `int if = 0;` - ![Invalid](https://img.shields.io/badge/Valid%3F-No-red)

6. **Pre-Defined Java class names and  interface as Identifiers** All pre-defined Java classnames and  interface can be used as Identifiers.
Even though it is valid, but it is not a good programming practice, because it reduces **Readability** and creates confusion.

    ``` java
    class Test {
        public static void main(String[] args) {
            int String = 888;
            System.out.println(String);
        }
    ```

    [![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen)](README.md) [![Not Recommended](https://img.shields.io/badge/Recommended%3F-No-red)](README.md) [![Output](https://img.shields.io/badge/Output%3F-888-brightgreen)](README.md)

    ``` java
    class Test {
        public static void main(String[] args) {
            int Runnable = 999;
            System.out.println(Runnable);
        }
    ```

    ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) ![Not_Recommended](https://img.shields.io/badge/Recommended%3F-No-red) ![Output](https://img.shields.io/badge/Output%3F-999-brightgreen)

---

### TEST

Q. Which of the following are **valid** Java identifiers?

|Sr. No. | Identifier | Answer |
|---|---|---|
| 1. | `total_number`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 2. | `total#`|  [![Invalid](https://img.shields.io/badge/Valid%3F-No-red)](#rules-for-defining-java-identifiers) Rule No.1 |
| 3. | `123total`| [![Invalid](https://img.shields.io/badge/Valid%3F-No-red)](#rules-for-defining-java-identifiers) Rule No.2 |
| 4. | `total123`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 5. | `ca$h`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 6. | `_$_$_$_$_`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 7. | `all@hands`| [![Invalid](https://img.shields.io/badge/Valid%3F-No-red)](#rules-for-defining-java-identifiers) Rule No.1 |
| 8. | `Integer`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) ![Not Recommended](https://img.shields.io/badge/Recommended%3F-No-red)|
| 9. | `Int`| ![Valid](https://img.shields.io/badge/Valid%3F-Yes-brightgreen) |
| 10. |`int`| [![Invalid](https://img.shields.io/badge/Valid%3F-No-red)](#rules-for-defining-java-identifiers) Rule No.5 |
---

### Next Topic: [1.02 Reserved Words](../02_reserved_words/README.md)
