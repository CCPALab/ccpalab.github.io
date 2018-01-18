---
title:  "Projects"
layout: single
permalink: /projects/
author_profile: true
comments: true
toc: true
toc_label: Projects
---

## UI-Lag-Finder
*Tool for detecting potential lags in UI threads*\\
<https://github.com/Devexperts/uilagfinder>

This tool finds potentially long operations invocations in UI thread. The long operation is determined as a method, which needs access to filesystem or network.  The approach is based on two main techniques – applying static analysis to widen the scope of detection and run-time code instrumentation to detect violations on the fly. Static analysis phase detects methods that contain potentially long operations on a Function Call Graph (FCG) and marks them as “long”. Collected data is used by the run-time part to widen the scope of analysis and report if a long operation is invoked in UI thread. The run-time analysis also detects if UI thread may be blocked too long due to acquiring a lock which could be held during a long operation invocation.
{: .text-justify}



## Lin-Check
*Framework for testing concurrent algorithms for correctness*\\
<https://github.com/Devexperts/lin-check>

Lin-Check is a testing framework for checking that concurrent data structure is linearizable. The approach is based on linearization definition and tries to find non-linearizable execution with specified operations, using a specially crafted test to produce lots of different executions. The execution is represented as a list of actors for every test thread, where the actor is the operation (e.g. put(key, value) and get(key) in java.util.Map) with already counted parameters.
{: .text-justify}

### Related talks
[Lock-free algorithms testing](http://nkoval.info/talks/#lock_free_algorithms_testing)



## Dl-Check
*Tool for finding potential deadlocks via dynamic analysis*\\
<https://github.com/Devexperts/dlcheck>

Dl-Check determines potential deadlock as a lock hierarchy violation and finds them via dynamic analysis in Java programs. This tool is implemented as Java agent and injects analysis code within class transformation during class loading, therefore it is possible to use Dl-Check without any code change. The base algorithm for finding lock hierarchy violations is based on new cycles detection in the lock-order graph. For this purpose, an algorithm for incremental topological order maintenance is used. However, existing solutions are not efficient for concurrent execution, so currently I am working on scalable topological order maintenance algorithm.
{: .text-justify}

### Related talks
[How to find deadlock not getting into it](http://nkoval.info/talks/#dl_check)

### Related publications
[Dl-Check: dynamic potential deadlock detection tool for Java programs](/publications/#dl_check_17)



## DRD
*Tool for dynamic detection of data races in Java programs*\\
<https://github.com/Devexperts/drd>

Data Race Detector (DRD) is a special tool for data races detection at run-time. DRD is implemented as Java agent and injects analysis code within class transformation during class loading, therefore it is possible to use DRD without any code change and under the same JVM. The tool uses vector clocks with some optimizations to detect data races, for every of which all needful to understand the race cause information is printed to a log file.
{: .text-justify}

### Related talks
[JPoint 2013: Dynamic data race detection in concurrent Java programs](http://2013.jpoint.ru/talks/18)\\
[SECR 2012: Dynamic data race detection in concurrent Java programs](http://2012.secr.ru/lang/ru-ru/talks/dynamic-data-race-detection-in-concurrent-java-programs)

### Related publications
[Dynamic data race detection in Java-programs using synchronization contracts](/publications/#drd_13)



## Usages
*Tool for finding code usages among Maven repositories*\\
<https://github.com/Devexperts/usages>

Usages tool finds code usages in the specified Maven repositories. It indexes repositories, downloads required artifacts and scans ".class" files in them. The tool analyzes all kinds of dependencies: usages of fields and methods, extensions of classes and implementations of interfaces, usages of annotations, overrides of methods. The tool is separated into 2 parts: server application, which collects all information and analyzes classes, and a client one, which is implemented as IntelliJ Plugin. 
{: .text-justify}

### Related talks
[SECR 2017: May I change this API a bit?...](http://2017.secr.ru/program/submitted-presentations/may-i-change-this-api-a-bit)



## Time-test
*Library for testing time-dependent functionality in Java programs*\\
<https://github.com/Devexperts/time-test>

TODO
{: .text-justify}

### Related posts
[Time machine for Java]()