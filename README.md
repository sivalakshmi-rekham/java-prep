# Java Prep

Java in depth and internal understanding

## Roadmap: Java Fundamentals to JVM Internals

This roadmap is organized by phases instead of days so you can move at your own pace. Each phase builds on the previous one and ends with practical exercises.

---

## Phase 1: Java Fundamentals and Core Syntax

Focus:
- Java basics: variables, operators, control flow, loops
- Arrays, strings, methods, exception handling
- Packages, access modifiers, static vs instance members
- Java class structure and project setup

Goal:
- Become comfortable writing and running Java programs
- Understand the language basics before diving into internals

Core topics:
- Primitive vs reference types
- Method overloading basics
- Static vs instance members
- Control flow and exception handling
- Basic I/O and Java project structure

Practice:
- Build small programs for calculations, parsing, file reading, and simple validation
- Use `javac` and `java` directly before moving to Maven/Gradle

References:
- Oracle Java Tutorials: https://docs.oracle.com/javase/tutorial/
- Java Language Basics: https://docs.oracle.com/javase/tutorial/java/nutsandbolts/
- JDK 17 Docs: https://docs.oracle.com/en/java/javase/17/

---

## Phase 2: Object-Oriented Programming and Java Semantics

Focus:
- Classes, objects, inheritance, interfaces, abstraction
- Polymorphism and dynamic dispatch
- Constructors, initialization order, static blocks
- Method overloading vs overriding
- Type casting, instanceof, autoboxing/unboxing
- Pass-by-value behavior in Java

Goal:
- Understand how Java object model works
- Clarify confusing language behaviors like casting and pass-by-value

Core topics:
- `this`, `super`, constructor chaining
- Interface vs abstract class
- Overriding rules and runtime dispatch
- `final`, `static`, `instanceof`
- Primitive widening/narrowing and reference casting
- Java passes references by value, not by reference

Practice:
- Write examples that show method overriding, constructor chaining, and reference mutation behavior
- Compare method overloading and overriding with actual outputs

References:
- Java OOP: https://docs.oracle.com/javase/tutorial/java/concepts/
- Interfaces and Inheritance: https://docs.oracle.com/javase/tutorial/java/IandI/
- Effective Java (Bloch): https://www.oreilly.com/library/view/effective-java/9780134686097/
- Java Tutorials - Classes and Objects: https://docs.oracle.com/javase/tutorial/java/javaOO/

---

## Phase 3: Collections, Data Structures, and Equality Semantics

Focus:
- `List`, `Set`, `Map`, `Queue`
- ArrayList, LinkedList, HashSet, LinkedHashSet, TreeSet
- HashMap, LinkedHashMap, TreeMap, Hashtable
- `equals()` and `hashCode()` contract
- Collections internal behavior and complexity

Goal:
- Learn not only how to use collections, but how they work internally
- Understand why equality and hashing matter in `HashMap` and `HashSet`

Core topics:
- Array resizing and amortized complexity
- Hash collisions and bucket chains
- Treeification in `HashMap`
- Map iteration and ordering
- Fail-fast iterators
- `equals()`/`hashCode()` contract and common mistakes

Practice:
- Implement simple versions of `HashMap` and `ArrayList` conceptually
- Write programs to observe collisions, resizing, and ordering behavior
- Test mutable keys in hash-based collections

References:
- Java Collections Framework: https://docs.oracle.com/javase/8/docs/technologies/library/coll/index.html
- `HashMap` source (OpenJDK): https://github.com/openjdk/jdk
- Java Collections Tutorial: https://docs.oracle.com/javase/tutorial/collections/
- Effective Java, Chapter on Objects and Collections: https://www.oreilly.com/library/view/effective-java/9780134686097/

---

## Phase 4: JVM Memory Model, Garbage Collection, and Safepoints

Focus:
- JVM memory areas: heap, stack, metaspace, native memory
- Object layout and reachability
- GC roots and garbage collection algorithms
- Young generation vs old generation
- Generational GC and promotion
- Safepoints and stop-the-world pauses

Goal:
- Understand how Java objects live, die, and get collected
- Learn how the JVM decides when to run GC

Core topics:
- Heap structure and generations
- Strong, soft, weak, and phantom references
- Mark-sweep, mark-compact, copying collectors
- Serial, Parallel, G1, ZGC, Shenandoah overview
- GC logs and basic tuning
- Safepoints: why they exist and what they do

Practice:
- Run programs with different heap sizes and GC settings
- Use `jcmd`, `jmap`, `jstat`, and `jstack`
- Inspect GC logs and analyze pause events

References:
- JVM Spec: https://docs.oracle.com/javase/specs/jvms/se17/html/
- HotSpot JVM docs: https://openjdk.org/
- G1 GC: https://docs.oracle.com/en/java/javase/17/gctuning/garbage-first-garbage-collector.html
- ZGC: https://openjdk.org/projects/zgc/
- Java GC Tuning Guide: https://docs.oracle.com/en/java/javase/17/gctuning/

---

## Phase 5: Multithreading, Synchronization, and Locks

Focus:
- Threads, executors, thread lifecycle, tasks
- `synchronized`, monitors, `wait()`, `notify()`
- `volatile`, happens-before, memory visibility
- Locks: `ReentrantLock`, `ReadWriteLock`, `Semaphore`, `CountDownLatch`, `CyclicBarrier`
- Atomic classes and thread safety
- Deadlocks, livelocks, starvation, contention

Goal:
- Understand how Java handles concurrency and memory visibility
- Learn how locks and synchronization work internally

Core topics:
- Thread safety and race conditions
- Java Memory Model basics
- `volatile` vs `synchronized`
- Intrinsic locks and monitor internals
- Lock contention and thread dumps
- `AtomicInteger`, `LongAdder`, `ConcurrentHashMap`

Practice:
- Write producer-consumer examples and deadlock demonstrations
- Analyze thread dumps using `jstack`
- Compare `synchronized`, `volatile`, and `Atomic*` behaviors

References:
- Java Concurrency Tutorial: https://docs.oracle.com/javase/tutorial/essential/concurrency/
- Java Memory Model: https://docs.oracle.com/javase/specs/jls/se17/html/jls-17.html
- Java Concurrency in Practice (Goetz): https://www.oreilly.com/library/view/java-concurrency-in/9780132702489/
- JDK concurrency docs: https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/package-summary.html

---

## Phase 6: Advanced Java Internals, Profiling, and Performance

Focus:
- JIT compilation and optimization basics
- Escape analysis and lock optimizations
- Profiling with JFR, Java Flight Recorder, async-profiler
- Benchmarking with JMH
- Heap analysis and memory leak detection
- High-performance design tradeoffs

Goal:
- Go beyond syntax and understand runtime optimization and performance behavior
- Learn how to diagnose bottlenecks and memory issues

Core topics:
- HotSpot JVM optimization
- CPU profiling vs memory profiling
- Object allocation hotspots
- Performance benchmarking rules
- GC tuning for throughput vs latency
- Memory leak diagnosis patterns

Practice:
- Profile a sample application using JFR or async-profiler
- Benchmark collections and synchronization choices with JMH
- Use heap analysis tools to inspect retention and leaks

References:
- Java Flight Recorder: https://docs.oracle.com/javacomponents/jmc-5-5/jfr-runtime-guide/
- JMH: https://openjdk.java.net/projects/code-tools/jmh/
- async-profiler: https://github.com/jvm-profilers/async-profiler
- VisualVM: https://visualvm.github.io/
- Java Performance (Hunt & John): https://www.oreilly.com/library/view/java-performance/9780137142528/

---

## Suggested Order of Study

1. Phase 1: Java fundamentals
2. Phase 2: OOP and Java semantics
3. Phase 3: Collections and `equals()`/`hashCode()`
4. Phase 4: Memory and GC internals
5. Phase 5: Multithreading and locks
6. Phase 6: Profiling and performance tuning

This order helps you build a strong foundation before moving into the internals of the JVM, GC, and concurrency.

---

## Recommended Reading List

- Head First Java (beginner-friendly)
- Effective Java (Bloch)
- Java Concurrency in Practice (Goetz)
- Java Performance (Hunt & John)
- The Java Language Specification
- The Java Virtual Machine Specification

---

## Core Interview Topics to Master

- `equals()` and `hashCode()` contract
- Constructor chaining, overloading, overriding
- Java pass-by-value behavior
- `HashMap` internals and collision handling
- Memory model and `volatile`
- `synchronized` vs `ReentrantLock`
- Garbage collection basics and safepoints
- Thread pool and executor patterns
- OOP principles and design tradeoffs

---

## Practical Rule

Do not just read. For each phase:
- write code
- run it
- observe output
- inspect JVM or GC behavior
- explain what is happening internally

That is the fastest way to move from Java basics to deep understanding.

---

## Contribution

This repository is meant to be a preparation guide for Java fundamentals and deep JVM-level understanding.

Update this README as your learning progresses and add notes, examples, and small projects under relevant folders.

