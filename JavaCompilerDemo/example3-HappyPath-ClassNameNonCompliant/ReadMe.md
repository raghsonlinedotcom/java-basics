# Explanation 

## Precursory - flow to set the stage 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % ls -l
total 8
-rw-r--r--  1 raghavan.muthu  staff  114 27 Aug 15:49 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % bat HelloWorld.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: HelloWorld.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ public class helloworld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % javac HelloWorld.java 
HelloWorld.java:1: error: class helloworld is public, should be declared in a file named helloworld.java
public class helloworld
       ^
1 error
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant %
```

### Explanation

As we know, the actual class name does not match with the source file name. The class name is all in lower case (`helloworld`) and the file name is in Sentence Case (`HelloWorld.java`) with the `.java` extension.

Hence the error, which we have already seen in the previous example. 

## Purposeful attempt to demonstrate this use case 

### Change the class name and the source file to all lower case

```sh
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % mv HelloWorld.java helloworld.java 
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % ls -ltrh
total 16
-rw-r--r--  1 raghavan.muthu  staff   114B 27 Aug 15:49 helloworld.java
-rw-r--r--  1 raghavan.muthu  staff   2.3K 27 Aug 15:51 ReadMe.md
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % bat helloworld.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: helloworld.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ public class helloworld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │ 
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```

We could see that we have successfully renamed the source file from `HelloWorld.java` (sentence case) to `helloworld.java` (all lower case), and the file name matches with the name of the class

### Attempt to compile the Java Source file `helloworld.java`

```sh
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % javac helloworld.java 
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % h
```

> *Note*: The compilation was successful as we expected. Since the filename matches _exactly_ with the class name, and henc no gap, and the `javac` (Java Compiler) was able to successfully compile the source code.

### List the files in the directory 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % ls -ltrh
total 24
-rw-r--r--  1 raghavan.muthu  staff   114B 27 Aug 15:49 helloworld.java
-rw-r--r--  1 raghavan.muthu  staff   2.3K 27 Aug 15:51 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 15:52 helloworld.class
```

> Note: We could see that the `.class` was properly generated in the same directory as expected. => `helloworld.class`


### Attempt to execute the file  

```sh
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant % java helloworld 
Hello World!
raghavan.muthu@Raghavans-MacBook-Pro example3-HappyPath-ClassNameNonCompliant %
```

> Note: The execution through `java` command was successful and we could see the program printing the expected output in the terminal/console.

## Conclusion

* The classname and the source file name - matches *exactly* 
* However, the classname is not in the _recommended_ format - hence *NonCompliant*. 
* But still it was allowed and hence was successfully compiled and executed

