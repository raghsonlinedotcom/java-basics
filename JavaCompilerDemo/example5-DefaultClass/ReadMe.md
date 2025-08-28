# ReadMe

## Java class is declared without any access modifier, but the filename is intact

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % pwd
/Users/raghavan.muthu/raghs/study/javapgms/basics/compilerDemo/example5-DefaultClass
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % ls -ltrh
total 16
-rw-r--r--  1 raghavan.muthu  staff   2.0K 27 Aug 16:03 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:04 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % bat HelloWorld.java 
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
```

* The Java class is declared without any access modifier like `public`, `protected` etc., hence having the default access
* The source file naming convention is intact - as though the class was declared with `public` access (`HelloWorld.java`) 

### Attempt to compile the file 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % javac HelloWorld.java 
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % 
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % ls -ltrh
total 24
-rw-r--r--  1 raghavan.muthu  staff   2.0K 27 Aug 16:03 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:04 HelloWorld.java
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 16:04 HelloWorld.class
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % 
```
> *Note*: The compilation with `javac` was successful. Though there is no access modifer to the class ,and there is *No mandate* that the source file name should exactly match with the Classname (similar to the class declared with public access), ), there is nothing wrong if the source file has an exact match with the classname, and that is what has happened in this case. 

> *Example*: We are expected to go in formal dress to the college/office, and we are not needed to follow the same rule inside the home. However, there is no harm if we dress up formally at home. 

## Explanation

The class did not have any access modifier - `public` , `protected` etc., Hence it is class with `default` access. 

The Java Compiler does not mandate any rule for the filename - as opposed to the filename being declared with the `public` keyword. Hence it compiled the source file successfully.

## Rename the source file `CompilerDemo.java` but the class name is intact `HelloWorld` 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % cp HelloWorld.java CompilerDemo.java
```

### List the files in the directory 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % ls -ltrh
total 32
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:04 HelloWorld.java
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 16:04 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff   2.6K 27 Aug 16:06 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:06 CompilerDemo.java
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % bat CompilerDemo.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: CompilerDemo.java
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
```

> *Note*: The class does not  have any access modifier/specifier like `public`, `protected` etc., However, the source file name is totally different - `CompilerDemo.java`

### Verifying the `.class` files in the folder 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % ls -ltrh *.class
-rw-r--r--  1 raghavan.muthu  staff   426B 27 Aug 16:04 HelloWorld.class
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % ls -ltrh CompilerDemo.class
ls: CompilerDemo.class: No such file or directory
```

> *Note*: There was only one `.class` file for `HelloWorld.class` and there is NOT `.class` file for the `CompilerDemo` in the directory.

### Attempt to compile the source code with the new name 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % javac CompilerDemo.java 
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % 
```

> *Note*: As expected, the `javac` (Java Compiler) had successfully compiled the source code/file. Because there is no rule for the source file to match with the class name (in exact case) since the class does _NOT_ have any access modifier. 

In such case, the source file name can be _anything_ - as long as it has the valid/allowed characters. 

The `javac` command did not produce anything in the terminal/console, proving that the compilation was succesful. 

### List the files in the directory - including the generated `.class` file 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % ls -ltrh
total 32
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:04 HelloWorld.java
-rw-r--r--  1 raghavan.muthu  staff   2.6K 27 Aug 16:06 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:06 CompilerDemo.java
-rw-r--r--  1 raghavan.muthu  staff   428B 27 Aug 16:07 HelloWorld.class
```

> *Note*: Though the `javac` has successfully compiled the source file, but the generated `.class` file has the name of the class and NOT the source file.

Here the class name is `HelloWorld` and the source file name is `CompilerDemo.java`.  

* If you expected the `.class` file to be `CompilerDemo.class`, it is _WRONG_. 
* The actual `.class` file generated is of the same class name -> `HelloWorld.class`, because we are compiling ONLY the classes and NOT the files. (_A Java class inside the source file - is what being compiled_).

> *Note*: You can also see the the timestamp of the `HelloWorld.class` has been modified with the current timestamp (`27 Aug 16:07`)


## Yet another attempt to demonstrate - by renaming the SourceFile to something different / arbitrary 


```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % cp CompilerDemo.java Raghavan.java
```

We have copied the source file from `CompilerDemo.java` to `Raghavan.java` -> just to take _any_ name.

### Verifying the files in the directory 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % ls -ltrh
total 40
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:04 HelloWorld.java
-rw-r--r--  1 raghavan.muthu  staff   2.6K 27 Aug 16:06 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:06 CompilerDemo.java
-rw-r--r--  1 raghavan.muthu  staff   428B 27 Aug 16:07 HelloWorld.class
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:09 Raghavan.java
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % bat Raghavan.java 
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: Raghavan.java
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
```

> *Note*: We could see that there are 3 source files - `HelloWorld.java` (original file), and the renamed files - `CompileDemo.java` and the recent one `Raghavan.java` - *all of them* having the _same class_ `HelloWorld`. 

### Attempt to compile the new source file `Raghavan.java`

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % javac Raghavan.java 
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % 
```

As expected, the source file was successfully compiled, because the file name does not matter for the class having the default access modifier. 

### Verify the files in the directory including the generated `.class` file for `Raghavan.java`

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % ls -ltrh
total 40
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:04 HelloWorld.java
-rw-r--r--  1 raghavan.muthu  staff   2.6K 27 Aug 16:06 ReadMe.md
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:06 CompilerDemo.java
-rw-r--r--  1 raghavan.muthu  staff   107B 27 Aug 16:09 Raghavan.java
-rw-r--r--  1 raghavan.muthu  staff   424B 27 Aug 16:09 HelloWorld.class
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % 
```

> *Note*: Again, as explained above, the generated `.class` file has the name of the class `HelloWorld` - as `HelloWorld.class`, and *NOT* the source file name  - like `Raghavan.class`. 

Repeat, we are compiling the class inside the source file and _NOT_ the source file itself. 

> *Note*: You can also see the the timestamp of the `HelloWorld.class` has been modified with the current timestamp (`27 Aug 16:09`)

### Attempt to execute the filename without extension 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % java Raghavan
Error: Could not find or load main class Raghavan
Caused by: java.lang.ClassNotFoundException: Raghavan
```

> *Note*: Here we are trying to execute a class named *Raghavan*, but we do NOT have any clas with the name `Raghavan`. Because the class name is `HelloWorld` - though the file names are different. 

### Executing the class with the right name 

```sh
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass % java HelloWorld 
Hello World!
raghavan.muthu@Raghavans-MacBook-Pro example5-DefaultClass %
```

> *Note*: Now, the attempt to execute the class with the right name was successful. 

