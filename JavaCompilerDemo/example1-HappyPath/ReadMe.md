# Explanation

```sh
raghavan.muthu@Raghavans-MacBook-Pro compilerDemo % ls -l
total 8
-rw-r--r--  1 raghavan.muthu  staff  114 27 Aug 15:21 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro compilerDemo % bat HelloWorld.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: HelloWorld.java
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

## Attempt to compile the Java Source File 

```sh
raghavan.muthu@Raghavans-MacBook-Pro compilerDemo % javac HelloWorld.java 
raghavan.muthu@Raghavans-MacBook-Pro compilerDemo %    
```

> Note: The compilation was successful and hence there was nothing printed (output or error) in the terminal (the control was returned to the prompt immediately) 

## List the folder/ directory to see the generated `.class` file 

```sh
raghavan.muthu@Raghavans-MacBook-Pro compilerDemo % ls   
HelloWorld.class	HelloWorld.java
```

## Verify the directory contents - listing shows the `.class` file generated 

```sh
raghavan.muthu@Raghavans-MacBook-Pro compilerDemo % ls -l
total 16
-rw-r--r--  1 raghavan.muthu  staff  426 27 Aug 15:22 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff  114 27 Aug 15:21 HelloWorld.java
```

## Execute the Class (and NOT the file)  

```sh
raghavan.muthu@Raghavans-MacBook-Pro compilerDemo % java HelloWorld 
Hello World!
raghavan.muthu@Raghavans-MacBook-Pro compilerDemo %
```

## Explanation

The source code file follows the norms - matching with the exact case of the Class and ends with a `.java` extension of a public class. Hence it got compiled successfully and we are also able to execute it further with the `java` (JRE). 

