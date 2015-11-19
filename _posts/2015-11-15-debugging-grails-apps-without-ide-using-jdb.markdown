---
layout: post
title:  "Debugging Grails Apps without IDE"
date: 2015-11-15 22:41:04
categories: grails
---
I'm a Sublime Text IDE fan, is simple, easy to use and has a lot of awesome packages, but for some programming languages have not a good support. Languages derived of JVM are a good sample of that.

One thing I miss in Sublime 3 is a debugger. These days I've been developing in Grails 3, for that case other IDEs (Eclipse, Netbeans or IntelliJ) don't have either real support for common tasks.

So one solution is to use Java Debugger (JDB). 

Here is a sample how you can debug a Grails App with JDB.

I have a Grails HelloWorld App, with one Controller called TestController.groovy:


    package com.hello

    class TestController {

        def index() {
            try {
                def s = "chao"
                render "hola!!"
            }
            catch(e) {
                log.error(e)
            }
        }
    }


It's time for run our app (with flag --debug-jvm):

`gradle run --debug-jvm`


And finally attach JDB to debugger our App.

`jdb -attach localhost:5005`


Now JDB is waiting for instructions, so I'll tell it to stop (set a breakpoint) when the execution comes to the line that begin with  `def s` within of index function.

`stop at com.hello.TestController:8`

Finally just write `run` in JDB to continue with the execution.

At this point when the execution pass for line 8, will stop, showing something like this:

`Breakpoint hit: "thread=http-nio-8080-exec-1", com.hello.TestController.index(), line=8 bci=116`

If you write `locals` this will be show you all vars inside of this scope.

Now you can debug a JVM application without a fancy IDE :-D




