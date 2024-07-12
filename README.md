# Java Version Features Cheatsheet 

## Java 9 (Sep 21, 2017)

Key Features:

1. Modular System (Project Jigsaw):

- Why Added: To modularize the JDK and make it more scalable and maintainable.
- How It Helps: Allows developers to create and use modules, improves application performance, and enhances security.

Example:
```
module com.example.myapp {
    requires java.base;
    exports com.example.myapp;
}
```

2. New HTTP Client:

- Why Added: To replace the old HttpURLConnection with a more modern and flexible API.
- How It Helps: Supports HTTP/2 and WebSocket, asynchronous requests, and cleaner API.

Example:

```

HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder()
    .uri(URI.create("https://example.com"))
    .build();
HttpResponse<String> response = client.send(request, BodyHandlers.ofString());
System.out.println(response.body());
```
3. Java 9 REPL (JShell):

- Why Added: To provide a read-eval-print loop for quickly testing and experimenting with Java code.
- How It Helps: Enhances productivity and learning experience.

Example:
```
jshell> int x = 10;
jshell> System.out.println(x + 2);
```


## Java 10 (Mar 20, 2018)

Key Features:

1. Local Variable Type Inference:

- Why Added: To reduce boilerplate code by allowing the var keyword for local variable declarations.
- How It Helps: Makes code more concise and readable.

Example:
```
var list = new ArrayList<String>();
list.add("example");
```

2. Garbage Collector Interface:

- Why Added: To provide a common interface for all garbage collectors.
- How It Helps: Simplifies the implementation and management of different garbage collectors.

Example:
```
This feature is internal and doesn't have direct API usage.
```

3. App Class-Data Sharing:

- Why Added: To improve startup and footprint by sharing class data across Java processes.
- How It Helps: Reduces memory usage and improves startup time.


## Java 11 (Sep 25, 2018) - LTS

Key Features:

1. HTTP Client (Standard):

- Why Added: To stabilize the new HTTP Client API introduced in Java 9.
- How It Helps: Offers a more powerful and flexible HTTP client.

Example:

```
HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder()
    .uri(URI.create("https://example.com"))
    .build();
HttpResponse<String> response = client.send(request, BodyHandlers.ofString());
System.out.println(response.body());
```

2. Dynamic Class-File Constants:

- Why Added: To allow dynamic constants in the class file.
- How It Helps: Supports more efficient class file structures and reduces duplication.

3. Epsilon GC (No-Op Garbage Collector):

- Why Added: For low-latency and high-throughput applications where GC pauses are undesirable.
- How It Helps: Offers predictable performance by not performing any garbage collection.


## Java 12 (Mar 19, 2019)

Key Features:

1. Switch Expressions (Preview):

- Why Added: To simplify switch statements and make them more expressive.
- How It Helps: Reduces boilerplate code and adds more flexibility to switch cases.

Example:
```
int numLetters = switch (day) {
    case MONDAY, FRIDAY, SUNDAY -> 6;
    case TUESDAY -> 7;
    case THURSDAY, SATURDAY -> 8;
    case WEDNESDAY -> 9;
    default -> throw new IllegalStateException("Unexpected value: " + day);
};
```

2. Teeing Collectors:

- Why Added: To allow collecting elements in multiple ways and combining the results.
- How It Helps: Simplifies collecting and combining data.

Example:

```
Collector<T, ?, R> collector = Collectors.teeing(
    Collectors.summingInt(T::getValue),
    Collectors.counting(),
    (sum, count) -> new Result(sum, count)
);
```

## Java 13 (Sep 17, 2019)

Key Features:

1. Text Blocks (Preview):

- Why Added: To simplify the creation of multiline strings.
- How It Helps: Reduces the need for escape sequences and improves readability.

Example:
```
String json = """
    {
        "name": "John",
        "age": 30,
        "city": "New York"
    }
    """;
```

2. Enhancements in Switch Expressions:

- Why Added: To further enhance the switch expression feature.
- How It Helps: Improves code readability and reduces errors.

Example:

```
    int result = switch (input) {
    case 1 -> 10;
    case 2 -> 20;
    default -> 0;
};
```
3. ZGC Improvements:

- Why Added: To improve the Z Garbage Collector's performance and scalability.
- How It Helps: Provides better pause time and memory management.


## Java 14 (Mar 17, 2020)

Key Features:

1. Pattern Matching for instanceof (Preview):

- Why Added: To simplify the type-checking and casting.
- How It Helps: Reduces boilerplate code and improves readability.

Example:

```
if (obj instanceof String s) {
    System.out.println(s.toLowerCase());
}
```

2. Records (Preview):

- Why Added: To provide a compact syntax for declaring data classes.
- How It Helps: Reduces boilerplate code for immutable data carriers.

Example:
```
public record Point(int x, int y) {}
```

3. JFR Event Streaming:

- Why Added: To enable continuous monitoring and diagnostics.
- How It Helps: Provides real-time visibility into application performance.

Example:
```
This feature is more about configuration and usage rather than code.
```
## Java 15 (Sep 15, 2020)

Key Features:

1. Sealed Classes (Preview):

- Why Added: To restrict which classes can extend or implement a given class or interface.
- How It Helps: Enhances encapsulation and security.

Example:

```
public sealed class Shape
    permits Circle, Square, Rectangle {}

public final class Circle extends Shape {}
public final class Square extends Shape {}
public final class Rectangle extends Shape {}
```
2. Hidden Classes:

- Why Added: To support frameworks that generate classes dynamically.
- How It Helps: Improves security and reduces memory footprint.

3. EdDSA (Edwards-Curve Digital Signature Algorithm):

- Why Added: To support new digital signature algorithms.
- How It Helps: Enhances cryptographic capabilities.

## Java 16 (Mar 16, 2021)

Key Features:

1. Records (Standard):

- Why Added: To stabilize the record feature introduced in Java 14.
- How It Helps: Provides a standard way to create immutable data classes.

Example:
```
public record Person(String name, int age) {}
```
2. Pattern Matching for instanceof (Standard):

- Why Added: To stabilize the pattern matching feature introduced in Java 14.
- How It Helps: Simplifies type-checking and casting.

Example:
```
if (obj instanceof String s) {
    System.out.println(s.toUpperCase());
}
```
3. Vector API (Incubator):

- Why Added: To provide a mechanism for expressing vector computations.
- How It Helps: Enables high-performance computing.

Example:
```
Vector<Integer> vector = Vector.of(1, 2, 3, 4);

```



## Java 17 (Sep 14, 2021) - LTS

Key Features:

1. Pattern Matching for switch (Preview):
- Why Added: To allow pattern matching in switch statements.
- How It Helps: Enhances the expressiveness and readability of switch statements.

 Example:
```
switch (obj) {
    case Integer i -> System.out.println("Integer: " + i
```


2. Sealed Classes (Standard):

- Why Added: To stabilize the sealed classes feature introduced in Java 15.
- How It Helps: Restricts which classes can extend or implement a given class or interface, enhancing security and encapsulation.

Example:
```
public sealed class Shape
    permits Circle, Square, Rectangle {}

public final class Circle extends Shape {}
public final class Square extends Shape {}
public final class Rectangle extends Shape {}
```

3. Foreign Function & Memory API (Incubator):

- Why Added: To provide a mechanism to interoperate with code and data outside of the JVM.
- How It Helps: Allows Java programs to call native libraries and manage memory outside of the Java heap.

Example:

```
try (MemorySegment segment = MemorySegment.allocateNative(100)) {
    MemoryAddress address = segment.baseAddress();
    // Use the address to interact with native memory
}
```

## Java 18 (Mar 22, 2022)

Key Features:

1. UTF-8 by Default:

- Why Added: To standardize character encoding.
- How It Helps: Ensures consistency across different environments and simplifies internationalization.

Example:
```
No direct code example needed, but it affects file operations and string handling.
```
2. Simple Web Server:

- Why Added: To provide a simple, out-of-the-box web server.
- How It Helps: Useful for prototyping, testing, and serving static content.

Example:
```
var server = SimpleFileServer.createFileServer(
    new InetSocketAddress(8000),
    Path.of("public"),
    SimpleFileServer.OutputLevel.VERBOSE
);
server.start();
```
3. Code Snippets in API Documentation:

- Why Added: To enhance Javadoc with executable snippets.
- How It Helps: Improves documentation quality and accuracy.

Example:
```
/**
 * {@snippet :
 * System.out.println("Hello, World!");
 * }
 */
public class Example {}
```

## Java 19 (Sep 20, 2022)

Key Features:

1. Record Patterns (Preview):

- Why Added: To enhance pattern matching with records.
- How It Helps: Simplifies data extraction from records.

Example:

```
record Point(int x, int y) {}
var point = new Point(1, 2);
if (point instanceof Point(int x, int y)) {
    System.out.println("x: " + x + ", y: " + y);
}
```

2. Virtual Threads (Preview):

- Why Added: To introduce lightweight threads.
- How It Helps: Improves the scalability of concurrent applications.

Example:
```
try (var scope = newVirtualThreadPerTaskExecutor()) {
    scope.submit(() -> System.out.println("Hello from virtual thread"));
}
```
3. Structured Concurrency (Incubator):

- Why Added: To simplify multithreaded programming.
- How It Helps: Makes concurrent code easier to read and maintain.

Example:
```
try (var scope = new StructuredTaskScope.ShutdownOnFailure()) {
    Future<String> future = scope.fork(() -> "Result");
    scope.join();  // join all tasks
    scope.throwIfFailed();  // propagate errors
    System.out.println(future.resultNow());
}
```

## Java 20 (Mar 21, 2023)

Key Features:

1. Scoped Values (Incubator):

- Why Added: To provide a better alternative to thread-local variables.
- How It Helps: Makes it easier to share immutable data across threads.

Example:
```
public static final ScopedValue<String> MY_VALUE = ScopedValue.newInstance();

ScopedValue.where(MY_VALUE, "Scoped data").run(() -> {
    System.out.println(MY_VALUE.get());
});
```

2. Virtual Threads (Preview):

- Why Added: Continued work on virtual threads.
- How It Helps: Further stabilizes and improves the feature for scalable concurrency.

Example:
```
var thread = Thread.ofVirtual().start(() -> System.out.println("Running in a virtual thread"));
thread.join();
```

## Java 21 (Sep 19, 2023) - LTS

Key Features:

1. Sequenced Collections:

- Why Added: To provide collections with predictable iteration order.
- How It Helps: Simplifies code that relies on iteration order.

Example:

```
SequencedCollection<String> collection = SequencedCollections.create();
collection.add("one");
collection.add("two");
collection.forEach(System.out::println);
```
2. Record Patterns:

- Why Added: To finalize the record patterns feature.
- How It Helps: Simplifies pattern matching with records.

Example:

```
record Point(int x, int y) {}
var point = new Point(1, 2);
if (point instanceof Point(int x, int y)) {
    System.out.println("x: " + x + ", y: " + y);
}
```
3. Virtual Threads:

- Why Added: To stabilize virtual threads.
- How It Helps: Makes concurrent programming more scalable.

Example:
```
var thread = Thread.ofVirtual().start(() -> System.out.println("Running in a virtual thread"));
thread.join();
```
4. Key Encapsulation Mechanism API:

- Why Added: To support cryptographic key encapsulation.
- How It Helps: Enhances security by simplifying key exchange.

Example:
```
KeyGenerator keyGen = KeyGenerator.getInstance("AES");
keyGen.init(256);
SecretKey secretKey = keyGen.generateKey();
```

## Java 22 (Mar 19, 2024)

Key Features:

1. Region Pinning for G1:

- Why Added: To improve the performance of the G1 garbage collector.
- How It Helps: Reduces pause times and enhances performance for applications with large heaps.

2. Foreign Function & Memory API (Standard):

- Why Added: To stabilize the API for interoperation with native code and memory.
- How It Helps: Provides a reliable way to manage memory and call native functions from Java.

Example:
```
try (MemorySegment segment = MemorySegment.allocateNative(100)) {
    MemoryAddress address = segment.baseAddress();
    // Use the address to interact with native memory
}
```
3. Unnamed Var & Patterns:

- Why Added: To support unnamed variables and pattern matching.
- How It Helps: Simplifies code by reducing the need for explicit variable names.

Example:

```
var list = List.of(1, 2, 3);
list.forEach(_ -> System.out.println(_));
```
