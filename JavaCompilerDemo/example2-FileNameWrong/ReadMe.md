# Explanation

## Purposefully renaming the source file from `HelloWorld.java` to `Helloworld.java`

```bash
raghavan.muthu@Raghavans-MacBook-Pro example2-FileNameWrong % ls -l
total 8
-rw-r--r--  1 raghavan.muthu  staff  114 27 Aug 15:27 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example2-FileNameWrong % mv HelloWorld.java Helloworld.java 
raghavan.muthu@Raghavans-MacBook-Pro example2-FileNameWrong % ls -l
total 8
-rw-r--r--  1 raghavan.muthu  staff  114 27 Aug 15:27 Helloworld.java
```

## Display the contents of the source code file `Helloworld.java` 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example2-FileNameWrong % bat Helloworld.java   
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: Helloworld.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ public class HelloWorld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```

## Attempt to compile the Java Source file 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example2-FileNameWrong % javac Helloworld.java 
Helloworld.java:1: error: class HelloWorld is public, should be declared in a file named HelloWorld.java
public class HelloWorld
       ^
1 error
raghavan.muthu@Raghavans-MacBook-Pro example2-FileNameWrong %
```

## Explanation

The file name was purposefully renamed with a lowercase `w` as `Helloworld.java` but the actual class name is `HelloWorld`, and hence the compiler rejected the request of compiling this file, because the basic rule of any Java Program is to have the file name in the exact case of a public class. 

