![GitHub forks](https://img.shields.io/github/forks/UnterrainerInformatik/java-splitstopwatch?style=social) ![GitHub stars](https://img.shields.io/github/stars/UnterrainerInformatik/java-splitstopwatch?style=social) ![GitHub repo size](https://img.shields.io/github/repo-size/UnterrainerInformatik/java-splitstopwatch) [![GitHub issues](https://img.shields.io/github/issues/UnterrainerInformatik/java-splitstopwatch)](https://github.com/UnterrainerInformatik/java-splitstopwatch/issues)

[![license](https://img.shields.io/github/license/unterrainerinformatik/FiniteStateMachine.svg?maxAge=2592000)](http://unlicense.org) [![Travis-build](https://travis-ci.org/UnterrainerInformatik/java-splitstopwatch.svg?branch=master)](https://travis-ci.org/github/UnterrainerInformatik/java-splitstopwatch) [![Twitter Follow](https://img.shields.io/twitter/follow/throbax.svg?style=social&label=Follow&maxAge=2592000)](https://twitter.com/throbax)



# SplitStopWatch

This class implements a simple stop-watch for debugging in Java.

Additionally to the normal stopWatch-functionality it may be used to debug out split-times as well. It measures the split-times and keeps track of the overall times in a variable.
Don't be afraid to stop the watch. Stopping doesn't mean you loose any value whatsoever. Think of it as a real-life stopWatch where you may press the start-button at any time after previously pressing the stop-button.

This class provides useful overloads that allow writing to a PrintStream in a way that your measurement doesn't get compromised (the stopWatch is paused while writing to the stream). You may initialize it with a PrintStream so that you can use all the overloads that take a string-argument or System.out is used as a default.
All the write-operations are performed as a printLine-call, so you don't need to close your assigned text with a newline-character.

This class is automatically created using millisecond-precision. If you want to enable nanoseconds-precision albeit performance impacts, though the impact of this is very small indeed, you may do so after creating the stopWatch via the setIsNanoPrecision-Setter.

All public methods within this class are synchronized so you may use it concurrently within many threads.
It has a property 'isActive' that defaults to true. When this is set to false all calls to this class are aborted within a single if-statement in the called method. This is a convenience function so that you may leave your logging-code in the production code. 

All of our projects facilitate the [Project Lombok][lombok]. So please download it and 'install' it in your preferred IDE by clicking on the downloaded jar-file. Then all compile-errors should vanish.  

#### Example

```java
SplitStopWatch ssw = new SplitStopWatch();
ssw.start("started.");
  Thread.sleep(10);
ssw.split("split.");
  Thread.sleep(10);
ssw.stop("stopped.");
```

#### Apache Maven artifact to use in your pom
```xml
<dependency>
    <groupId>info.unterrainer.tools</groupId>
    <artifactId>splitstopwatch</artifactId>
    <version>0.3.0</version>
</dependency>
```

---
This program is brought to you by [Unterrainer Informatik][homepage]  
Project lead is [Psilo][psilomail]

[psilomail]: mailto:psilo@unterrainer.info
[lombok]: https://projectlombok.org

[github]: https://github.com/UnterrainerInformatik/java-splitstopwatch