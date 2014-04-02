# Building a simple Java command line program

I wanted to build the minimum possible command line program in Java. I took a
simple password changing program I found, built it using `javac`, and then built a JAR file with the executable class specified in the JAR creation.

The program is runnable with the Java application launcher using the `-jar` option: `java -jar path/to/program.jar`.

## Project Structure:

```
├── README.md
├── bin
│   └── app.jar
└── src
    ├── Password.class
    └── Password.java
```

*src/Password.java* The application's code. It's a class with a `public static void main` method. It was important for `jar` to find and load the main class that the `Password` class was declared in a package (`src`, the directory containing it in this case).

*src/Password.class* The compiled class file:

    javac src/Password.java
    => src/Password.class

*bin/app.jar* - The built jar file, containing the relevent reference to the main class. This is built by using the jar command:

    jar cfe bin/app.jar src.Password src/Password.class
    => bin/app.jar

The `app.jar` program can now be executed with the Java application launcher:

    java -jar bin/app.jar

## References:

- http://docs.oracle.com/javase/tutorial/displayCode.html?code=http://docs.oracle.com/javase/tutorial/essential/io/examples/Password.java
- http://docs.oracle.com/javase/tutorial/deployment/jar/appman.html
- http://www.tutorialspoint.com/java/java_packages.htm
- http://stackoverflow.com/a/804508/484820
