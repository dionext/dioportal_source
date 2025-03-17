---
title: "Java tips"
description: ""
keywords: ""
lang: "en"
permalink: "java-tips"
aliases:
  - "java-tips"
---

# Java tips

## Short blocks of code

### Anonymous Classes

[https://docs.oracle.com/javase/tutorial/java/javaOO/anonymousclasses.html](https://docs.oracle.com/javase/tutorial/java/javaOO/anonymousclasses.html)

The anonymous class expression consists of the following:

* The new operator

* The name of an interface to implement or a class to extend. In this example, the anonymous class is implementing the interface HelloWorld.

* Parentheses that contain the arguments to a constructor, just like a normal class instance creation expression. Note: When you implement an interface, there is no constructor, so you use an empty pair of parentheses, as in this example.

* A body, which is a class declaration body. More specifically, in the body, method declarations are allowed but statements are not.

Example:

```
public class HelloWorldAnonymousClasses {
  
    interface HelloWorld {
        public void greet();
        public void greetSomeone(String someone);
    }
  
    public void sayHello() {
        
        HelloWorld frenchGreeting = new HelloWorld() {
            String name = "tout le monde";
            public void greet() {
                greetSomeone("tout le monde");
            }
            public void greetSomeone(String someone) {
                name = someone;
                System.out.println("Salut " + name);
            }
        };
        
}
```

Example with override class form lib:

```
        btn.setOnAction(new EventHandler<ActionEvent>() {
 
            @Override
            public void handle(ActionEvent event) {
                System.out.println("Hello World!");
            }
        });
```

### Lambda

Anonymous class seems a bit excessive and cumbersome. Lambda expressions let you express instances of single-method classes more compactly.

[https://www.w3schools.com/java/java\_lambda.asp](https://www.w3schools.com/java/java_lambda.asp)

A lambda expression is a short block of code which takes in parameters and returns a value. Lambda expressions are similar to methods, but they do not need a name and they can be implemented right in the body of a method.

(parameter1, parameter2) -\> expression

(parameter1, parameter2) -\> { code block }

Example:

```
ArrayList<Integer> numbers = new ArrayList<Integer>();
numbers.forEach( (n) -> { System.out.println(n); } );
```

    ArrayList<Integer> numbers = new ArrayList<Integer>();
    Consumer<Integer> method = (n) -> { System.out.println(n); };
    numbers.forEach( method );

To use a lambda expression in a method, the method should have a parameter with a single-method interface as its type. Calling the interface's method will run the lambda expression

```
interface StringFunction {
  String run(String str);
}

public class Main {
  public static void main(String[] args) {
    StringFunction exclaim = (s) -> s + "!";
    StringFunction ask = (s) -> s + "?";
    printFormatted("Hello", exclaim);
    printFormatted("Hello", ask);
  }
  public static void printFormatted(String str, StringFunction format) {
    String result = format.run(str);
    System.out.println(result);
  }
}
```

### Consumer, Predicate, Supplier, and Function {\#9857}

[https://medium.com/javarevisited/java-8s-consumer-predicate-supplier-and-function-bbc609a29ff9](https://medium.com/javarevisited/java-8s-consumer-predicate-supplier-and-function-bbc609a29ff9)

A Consumer is an in-build functional interface in the java.util.function package. we use consumers when we need to consume objects, the consumer takes an input value and returns nothing.

```
Consumer<String> printConsumer= city-> System.*out*.println(city);
```

A Predicate is a functional interface, which accepts an argument and returns a boolean. Usually, it is used to apply in a filter for a collection of objects.

```
Predicate<String> filterCity = city -> city.equals("Mumbai");
   cities.stream().filter(filterCity).forEach(System.*out*::println);
```

A**Function** is another in-build functional interface in `java.util.function `package, the function takes an input value and returns a value.

```
Function<String, Character> getFirstCharFunction = city -> {
        returncity.charAt(0);
    };
cities.stream().map(getFirstCharFunction)
                   .forEach(System.*out*::println);
```

```
 
```

The Supplier Interface is a part of the java.util.function package. It represents a function that does not take in any argument but produces a value of type T. It contains only one method.

```

Supplier<String[]> citySupplier = () -> {
        return newString[]{"Mumbai", "Delhi", "Goa", "Pune"};
    };
Arrays.asList(citySupplier.get()).forEach(System.*out*::println);
```

The BinaryOperator Interface\<T\> is a part of the java.util.function package which has been introduced since Java 8, to implement functional programming in Java. It represents a binary operator which takes two operands and operates on them to produce a result. However, what distinguishes it from a normal BiFunciton is that both of its arguments and its return type are same.

```
        BinaryOperator<Integer> divide = (a, b) -> {
            double divisionResult = (double) a / b;
            // Round the result, and return it as an integer
            return (int) Math.round(divisionResult);
        };
```

## Java text block

[https://docs.oracle.com/en/java/javase/21/text-blocks/index.html](https://docs.oracle.com/en/java/javase/21/text-blocks/index.html)

### Using a text block

(java 15+)

A text block can be used in place of a string literal to improve the readability and clarity of the code. This primarily occurs when a string literal is used to represent a multi-line string. In this case there is considerable clutter from quotation marks, newline escapes, and concatentation operators.

```java

// ORIGINAL
String message = "'The time has come,' the Walrus said,\n" +
                 "'To talk of many things:\n" +
                 "Of shoes -- and ships -- and sealing-wax --\n" +
                 "Of cabbages -- and kings --\n" +
                 "And why the sea is boiling hot --\n" +
                 "And whether pigs have wings.'\n";
```

Using text blocks removes much of the clutter:

```java

// BETTER
String message = """
    'The time has come,' the Walrus said,
    'To talk of many things:
    Of shoes -- and ships -- and sealing-wax --
    Of cabbages -- and kings --
    And why the sea is boiling hot --
    And whether pigs have wings.'
    """;
```

The example below uses "·" to visualize the incidental white space, with essential white space shown as actual white space.

```java

void writeHTML() {
    String html = """
········<html>
········    <body>
········        <p>Hello World.</p>
········    </body>
········</html>
········""";
    writeOutput(html);
}
```

After the incidental white space is stripped, the resulting contents of the text block are as follows:

```html

<html>
    <body>
        <p>Hello World.</p>
    </body>
</html>
```

How to avoid inserting last line break if it is not needed

```java

String html1 = """
	<a href=\
	"""
	+ hrefUrl +
	"""
        ">""";
```

```java
String html2 = """
	<a href=\""""
	+ hrefUrl +
	"""
        ">""";
```

```java
String html3 = """
	<a href=" """
	+ hrefUrl +
	"""
        ">""";
```

```
 
```

Recommendation:

* You should use a text block when it improves the clarity of the code, particularly with multi-line strings
* If a string fits on a single line, without concatenation and escaped newlines, you should probably continue to use a string literal
* For most multi-line strings, place the opening delimiter at the right end of the previous line, and place the closing delimiter on its own line, at the left margin of the text block
* Either use only spaces or only tabs for the indentation of a text block. Mixing white space will lead to a result with irregular indentation

Note: Show non-printable characters in IntelliJ IDEA [https://intellij-support.jetbrains.com/hc/en-us/community/posts/207045165-Show-non-printable-characters-Tabs](https://intellij-support.jetbrains.com/hc/en-us/community/posts/207045165-Show-non-printable-characters-Tabs)

* View | Active Editor | Show Whitespaces -- affects current tab only
* Settings | Editor | Appearance --\> Show whitespaces -- affects all (newly opened) tabs

## Java String Templates

[https://www.baeldung.com/java-21-string-templates](https://www.baeldung.com/java-21-string-templates)

[https://belief-driven-design.com/looking-at-java-21-string-templates-c7cbc/](https://belief-driven-design.com/looking-at-java-21-string-templates-c7cbc/)

### String Formatter

```java

String html4 = String.format("""
  			<a href="%s">
   			""", hrefUrl);
```

### MessageFormat Class

```
		String html5 = MessageFormat.format("""
    			<a href="{0}">
    			""", hrefUrl);
```

### STR Template Processor

[https://docs.oracle.com/en/java/javase/21/language/string-templates.html#GUID-771D8AC4-EAE6-456D-A476-306717F75C0C](https://docs.oracle.com/en/java/javase/21/language/string-templates.html#GUID-771D8AC4-EAE6-456D-A476-306717F75C0C)

[https://mail.openjdk.org/pipermail/amber-spec-experts/2024-April/004106.html](https://mail.openjdk.org/pipermail/amber-spec-experts/2024-April/004106.html) Update on String Templates (JEP 459) - (There will be no String Template in JDK 23)

```java

String  html6 = STR."""
  			<a href="\{hrefUrl}">
  			""";
```

Note: in Java 21 use "--enable preview" to enable STR [https://stackoverflow.com/questions/72083752/enable-preview-features-in-an-early-access-version-of-java-in-intellij](https://stackoverflow.com/questions/72083752/enable-preview-features-in-an-early-access-version-of-java-in-intellij)

```java

```

## JSON - Java Bean convert

Online convertors

[https://json2csharp.com/code-converters/json-to-pojo](https://json2csharp.com/code-converters/json-to-pojo)

[https://www.jsonschema2pojo.org/](https://www.jsonschema2pojo.org/)
