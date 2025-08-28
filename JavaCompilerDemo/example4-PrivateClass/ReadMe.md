# Explanation

```sh
raghavan.muthu@Raghavans-MacBook-Pro example4-PrivateClass % pwd
/Users/raghavan.muthu/raghs/study/javapgms/basics/compilerDemo/example4-PrivateClass
raghavan.muthu@Raghavans-MacBook-Pro example4-PrivateClass % ls -ltrh
total 8
-rw-r--r--  1 raghavan.muthu  staff   115B 27 Aug 16:02 HelloWorld.java
raghavan.muthu@Raghavans-MacBook-Pro example4-PrivateClass % bat HelloWorld.java
───────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: HelloWorld.java
───────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ private class HelloWorld
   2   │ {
   3   │     public static void main(String... args)
   4   │     {
   5   │         System.out.println("Hello World!");
   6   │     }
   7   │ }
   8   │
───────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
raghavan.muthu@Raghavans-MacBook-Pro example4-PrivateClass % javac HelloWorld.java
HelloWorld.java:1: error: modifier private not allowed here
private class HelloWorld
        ^
1 error
raghavan.muthu@Raghavans-MacBook-Pro example4-PrivateClass %
```

