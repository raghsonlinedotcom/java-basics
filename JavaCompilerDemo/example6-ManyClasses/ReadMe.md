# ReadMe

## Normal Scenario - HappyPath - for a class with the default access

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % pwd
/Users/raghavan.muthu/raghs/study/javapgms/basics/compilerDemo/example6-ManyClasses
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 8
-rw-r--r--  1 raghavan.muthu  staff     0B 27 Aug 17:04 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 17:04 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % bat HelloWorld.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: HelloWorld.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ class HelloWorld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % javac HelloWorld.java 
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 16
-rw-r--r--  1 raghavan.muthu  staff     0B 27 Aug 17:04 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 17:04 HelloWorld.java
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 17:05 HelloWorld.class
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % java HelloWorld 
Hello World!
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % 
```

### Explanation

* The class has the default access 
* The source file need not have the same / exact matching case with the Class name
* The source file still follows the norms, and has the name exactly matching with the name of the class &rarr; `HelloWorld.java`
* The Compilation through `javac` and the execution through `java` were successful

## Adding a new class in the Source file - `Demo`

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 24
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 17:05 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff   2.7K 27 Aug 17:07 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   123B 27 Aug 17:08 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % bat HelloWorld.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: HelloWorld.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ class HelloWorld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
   9   │ class Demo
  10   │ {
  11   │ }
  12   │ 
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```

> *Note*: The source file has got two classes `HelloWorld` (our usual) and the `Demo` - the newly added one at the bottom.

> The `Demo` class is empty, but it does not matter here. Just for the sake of demonstration, we added an empty class, which is very legal. _You can always have an empty class!_

### Attempt to compile the source file `HelloWorld.java` with two classes

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % javac HelloWorld.java 
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % 
```

> *Result*: The compilation was successful - as the `javac` command did not produce any output/error in the console.

### Verify the list of generated files in the folder/directory

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 32
-rw-r--r--  1 raghavan.muthu  staff   2.7K 27 Aug 17:07 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   123B 27 Aug 17:08 HelloWorld.java
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 17:08 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff   188B 27 Aug 17:08 Demo.class
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses %
```

#### Observations 

* There were two `.class` files separately generated - one for each Class. `HelloWorld.class` and `Demo.class`
* The classes were compiled in order - matching with the position in the source file 
* The `HelloWorld.class` was recompiled - freshly, and the timestamp of the .class file is evident `27 Aug 17:08`

## Attempt to execute the classes

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 40
-rw-r--r--  1 raghavan.muthu  staff   123B 27 Aug 17:08 HelloWorld.java
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 17:08 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff   188B 27 Aug 17:08 Demo.class
-rw-r--r--  1 raghavan.muthu  staff   6.0K 27 Aug 17:16 ReadMe.md
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % java HelloWorld 
Hello World!
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % java Demo       
Error: Main method not found in class Demo, please define the main method as:
   public static void main(String[] args)
or a JavaFX application class must extend javafx.application.Application
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % 
```

### Summary

* The execution of the `HelloWorld` class was successful since it has the PSVM (`public static void main()`) method
* The execution of the `Demo` class was unsuccessful since it is empty (does not have the PSVM method), and hence the JRE threw a meaningful error stating the gap.

## Scenario #2 - Added a new public class in the Source file `HelloWorld.java`

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 40
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 17:08 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff   188B 27 Aug 17:08 Demo.class
-rw-r--r--  1 raghavan.muthu  staff   7.1K 27 Aug 17:19 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   149B 27 Aug 17:55 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % bat HelloWorld.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: HelloWorld.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ class HelloWorld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
   9   │ class Demo
  10   │ {
  11   │ }
  12   │ 
  13 + │ public class Example
  14 + │ {
  15 + │ }
  16 + │ 
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % rm -rf *.class
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 24
-rw-r--r--  1 raghavan.muthu  staff   7.1K 27 Aug 17:19 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   149B 27 Aug 17:55 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % 
```

### An attempt to compile the Source file 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % javac HelloWorld.java 
HelloWorld.java:13: error: class Example is public, should be declared in a file named Example.java
public class Example
       ^
1 error
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh *.class
zsh: no matches found: *.class
```

> *Note*: As expected, the compiler did not generate any `.class` file - not even partially, as there was a failure and it also gave a suitable suggestion to make it work.

### Make it work - rename the file `HelloWorld.java` to `Example.java`

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 24
-rw-r--r--  1 raghavan.muthu  staff   7.1K 27 Aug 17:19 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   149B 27 Aug 17:55 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % mv HelloWorld.java Example.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 24
-rw-r--r--  1 raghavan.muthu  staff   7.1K 27 Aug 17:19 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   149B 27 Aug 17:55 Example.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % bat Example.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: Example.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ class HelloWorld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
   9   │ class Demo
  10   │ {
  11   │ }
  12   │ 
  13   │ public class Example
  14   │ {
  15   │ }
  16   │ 
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % javac Example.java 
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses %  
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 48
-rw-r--r--  1 raghavan.muthu  staff   7.1K 27 Aug 17:19 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   149B 27 Aug 17:55 Example.java
-rw-r--r--  1 raghavan.muthu  staff   423B 27 Aug 17:59 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff   185B 27 Aug 17:59 Demo.class
-rw-r--r--  1 raghavan.muthu  staff   188B 27 Aug 17:59 Example.class
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % 
```

### Summary

We made it work by renaming the Source file from `HelloWorld.java` to `Example.java` and everything went well. 

## Scenario #3 - Purposefully declaring more than one class in the Source File as `public`

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -l
total 64
-rw-r--r--  1 raghavan.muthu  staff    185 27 Aug 17:59 Demo.class
-rw-r--r--  1 raghavan.muthu  staff    188 27 Aug 17:59 Example.class
-rw-r--r--  1 raghavan.muthu  staff    149 27 Aug 17:55 Example.java
-rw-r--r--  1 raghavan.muthu  staff    423 27 Aug 17:59 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff  13172 27 Aug 18:03 ReadMe.md
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % rm -rf *.class
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 40
-rw-r--r--  1 raghavan.muthu  staff   149B 27 Aug 17:55 Example.java
-rw-r--r--  1 raghavan.muthu  staff    13K 27 Aug 18:03 ReadMe.md
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % vi Example.java 
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % bat Example.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: Example.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1 ~ │ public class HelloWorld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
   9   │ class Demo
  10   │ {
  11   │ }
  12   │ 
  13   │ public class Example
  14   │ {
  15   │ }
  16   │ 
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % git diff Example.java 
diff --git a/example6-ManyClasses/Example.java b/example6-ManyClasses/Example.java
index 1ed9d8a..66a01f5 100644
--- a/example6-ManyClasses/Example.java
+++ b/example6-ManyClasses/Example.java
@@ -1,4 +1,4 @@
-class HelloWorld
+public class HelloWorld
 {
 	public static void main(String... args)
 	{
```

### Attempt to compile the Source file `Example.java` 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % javac Example.java 
Example.java:1: error: class HelloWorld is public, should be declared in a file named HelloWorld.java
public class HelloWorld
       ^
1 error
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % 
```

### Observations

* The compilation was unsuccessful as the name of the Source file does not match with the name of the 1st public class in the Source File encountered by the Compiler &rarr; `HelloWorld`
* There is an order followed - as the classes are declared in the Source file
* There is another public class `Example` at the bottom, which was still actually successfully compiled, because of the good match with the class name Vs the source file name. Hence there was no error reported against that class. 

## Extended example to show the compiler does its job perfectly

```sh
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 48
-rw-r--r--  1 raghavan.muthu  staff    19K 27 Aug 18:15 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   180B 27 Aug 18:16 Example.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % bat Example.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: Example.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ class HelloWorld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
   9   │ public class Demo
  10   │ {
  11   │ }
  12   │ 
  13   │ public class Example
  14   │ {
  15   │ }
  16   │ 
  17 + │ public class Sample
  18 + │ {
  19 + │ }
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % javac Example.java 
Example.java:9: error: class Demo is public, should be declared in a file named Demo.java
public class Demo
       ^
Example.java:17: error: class Sample is public, should be declared in a file named Sample.java
public class Sample
       ^
2 errors
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % ls -ltrh
total 48
-rw-r--r--  1 raghavan.muthu  staff    19K 27 Aug 18:15 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   180B 27 Aug 18:16 Example.java
raghavan.muthu@Raghavans-MacBook-Pro example6-ManyClasses % 
```

### Summary

The compiler reports all the errors - the non matching classes with the file name - *all at once*.

In this case, apart from the class with default access (`HelloWorld`), there are three public classes in the Source File - `Demo.java`, `Example.java` and `Sample.java` and the compiler performs its operation as follows.

| Class Name  | Access Specifier | File Name | Compilation Status | Remarks | 
| ----------- | ---------------- | --------- | ------------------ | ------- |
| `HelloWorld`| `None` (default) | `Example.java` | Pass   | The class does not have any access modifier, and hence the file name does not matter |
| `Demo`      | `public`         | `Example.java` | Fail | The class is declared with the `public` access, but the source file name is different - `Example.java`. There is a mismatch, and hence the failure. |
| `Example`   | `public`         | `Example.java` | Pass | The class is declared with the `public` access, and the source file name is same - `Example.java`. There is a match, and hence the clearancee. |
| `Sample`      | `public`         | `Example.java` | Fail | The class is declared with the `public` access, but the source file name is different - `Example.java`. There is a mismatch, and hence the failure. |
