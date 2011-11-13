REPL bug
--------

* My Operating System (WinXP)
* Leiningen version

```
PS C:\mydocs\Clojure\repl-tester> lein version
Leiningen 1.6.2-SNAPSHOT on Java 1.7.0_01 Java HotSpot(TM) Client VM
```

How to reproduce
----------------

```cmd
PS C:\mydocs\Clojure\repl-tester> lein repl
REPL started; server listening on localhost port 49150
repl_tester.init=> (System/exit 0)
Exception in thread "Thread-3" java.lang.RuntimeException: java.net.SocketException: Connection reset
        at clojure.lang.AFn.run(AFn.java:28)
        at java.lang.Thread.run(Unknown Source)
Caused by: java.net.SocketException: Connection reset
        at java.net.SocketInputStream.read(Unknown Source)
        at java.net.SocketInputStream.read(Unknown Source)
        at sun.nio.cs.StreamDecoder.readBytes(Unknown Source)
        at sun.nio.cs.StreamDecoder.implRead(Unknown Source)
        at sun.nio.cs.StreamDecoder.read(Unknown Source)
        at java.io.InputStreamReader.read(Unknown Source)
        at java.io.Reader.read(Unknown Source)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
        at java.lang.reflect.Method.invoke(Unknown Source)
        at clojure.lang.Reflector.invokeMatchingMethod(Reflector.java:90)
        at clojure.lang.Reflector.invokeInstanceMethod(Reflector.java:28)
        at leiningen.repl$copy_out_loop.invoke(repl.clj:88)
        at leiningen.repl$repl_client$fn__1366.invoke(repl.clj:94)
        at clojure.lang.AFn.run(AFn.java:24)
        ... 1 more

Exception in thread "main" java.lang.reflect.InvocationTargetException
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
        at java.lang.reflect.Method.invoke(Unknown Source)
        at jline.ConsoleRunner.main(ConsoleRunner.java:69)
Caused by: java.net.SocketException: Connection reset by peer: socket write error (NO_SOURCE_FILE:0)
        at clojure.lang.Compiler.eval(Compiler.java:5440)
        at clojure.lang.Compiler.eval(Compiler.java:5391)
        at clojure.core$eval.invoke(core.clj:2382)
        at clojure.main$eval_opt.invoke(main.clj:235)
        at clojure.main$initialize.invoke(main.clj:254)
        at clojure.main$script_opt.invoke(main.clj:270)
        at clojure.main$main.doInvoke(main.clj:354)
        at clojure.lang.RestFn.invoke(RestFn.java:457)
        at clojure.lang.Var.invoke(Var.java:377)
        at clojure.lang.AFn.applyToHelper(AFn.java:172)
        at clojure.lang.Var.applyTo(Var.java:482)
        at clojure.main.main(main.java:37)
        ... 5 more
Caused by: java.net.SocketException: Connection reset by peer: socket write error
        at java.net.SocketOutputStream.socketWrite0(Native Method)
        at java.net.SocketOutputStream.socketWrite(Unknown Source)
        at java.net.SocketOutputStream.write(Unknown Source)
        at sun.nio.cs.StreamEncoder.writeBytes(Unknown Source)
        at sun.nio.cs.StreamEncoder.implFlushBuffer(Unknown Source)
        at sun.nio.cs.StreamEncoder.implFlush(Unknown Source)
        at sun.nio.cs.StreamEncoder.flush(Unknown Source)
        at java.io.OutputStreamWriter.flush(Unknown Source)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
        at java.lang.reflect.Method.invoke(Unknown Source)
        at clojure.lang.Reflector.invokeMatchingMethod(Reflector.java:90)
        at clojure.lang.Reflector.invokeNoArgInstanceMember(Reflector.java:265)
        at leiningen.repl$repl_client.doInvoke(repl.clj:99)
        at clojure.lang.RestFn.invoke(RestFn.java:442)
        at leiningen.repl$connect_to_server.invoke(repl.clj:105)
        at leiningen.repl$poll_repl_connection$fn__1371.invoke(repl.clj:112)
        at leiningen.repl$poll_repl_connection.invoke(repl.clj:112)
        at leiningen.repl$repl.invoke(repl.clj:152)
        at clojure.lang.Var.invoke(Var.java:365)
        at clojure.lang.AFn.applyToHelper(AFn.java:161)
        at clojure.lang.Var.applyTo(Var.java:482)
        at clojure.core$apply.invoke(core.clj:542)
        at leiningen.core$apply_task.invoke(core.clj:255)
        at leiningen.core$_main.doInvoke(core.clj:321)
        at clojure.lang.RestFn.invoke(RestFn.java:410)
        at clojure.lang.AFn.applyToHelper(AFn.java:161)
        at clojure.lang.RestFn.applyTo(RestFn.java:132)
        at clojure.core$apply.invoke(core.clj:542)
        at leiningen.core$_main.invoke(core.clj:324)
        at user$eval291.invoke(NO_SOURCE_FILE:1)
        at clojure.lang.Compiler.eval(Compiler.java:5424)
        ... 16 more
```

Copyright (C) 2011 FIXME

Distributed under the Eclipse Public License, the same as Clojure.
