---
title: Logging
layout: reference
---


<h1><a name="logging_for_blocks" id="logging_for_blocks">Logging</a></h1>

<div class="level1">

<p>

When implementing a system, you will be given a choice of predefined logging frameworks using SLF4J, depending on your destination platform, and the <a href="/doc/logging_for_blocks" class="wikilink1" title="doc:logging_for_blocks">log level</a> you wish to implement for. All necessary JAR files will be copied into your project and made available. 
</p>

<p>
<a href="/_detail/doc/choosing-logging-framework-java-se.png?id=doc%3Alogging" class="media" title="doc:choosing-logging-framework-java-se.png"><img src="/_media/doc/choosing-logging-framework-java-se.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Logging" [1-366] -->
<h3><a name="frameworks_for_java_seosgi_junit_test_suite" id="frameworks_for_java_seosgi_junit_test_suite">Frameworks for Java SE/OSGi, JUnit Test Suite</a></h3>
<div class="level3">

</div>

<h5><a name="logback" id="logback">Logback</a></h5>
<div class="level5">

<p>
Configuration via config file (<em>logback.xml</em> in <em>source-catalog/classpath</em>) or configuration object. See <a href="http://logback.qos.ch/manual/configuration.html" class="urlextern" title="http://logback.qos.ch/manual/configuration.html"  rel="nofollow">Configuration with Logback</a> for details.

</p>

</div>

<h5><a name="javautillogging" id="javautillogging">java.util.Logging</a></h5>
<div class="level5">

<p>
Configuration via config file (<em>logging.properties</em> located either in <em>&lt;jre&gt;/lib</em>/ or via command line: <code>java -Djava.util.logging.config.file=“mylocation/logging.properties”</code>) or configuration object. See 
<a href="http://docs.oracle.com/javase/7/docs/api/java/util/logging/LogManager.html" class="urlextern" title="http://docs.oracle.com/javase/7/docs/api/java/util/logging/LogManager.html"  rel="nofollow">Configuration with JUL</a> for details.

</p>

</div>

<h5><a name="log4j" id="log4j">Log4J</a></h5>
<div class="level5">

<p>
Configuration via config file (<em>log4j.properties</em>) or configuration object. See 
<a href="http://logging.apache.org/log4j/1.2/manual.html" class="urlextern" title="http://logging.apache.org/log4j/1.2/manual.html"  rel="nofollow">Configuration with Log4J</a> for details.

</p>

</div>

<h5><a name="systemout" id="systemout">System.out()</a></h5>
<div class="level5">

<p>
Configuration via configuration object as described at <a href="http://www.slf4j.org/api/org/slf4j/impl/SimpleLogger.html" class="urlextern" title="http://www.slf4j.org/api/org/slf4j/impl/SimpleLogger.html"  rel="nofollow">Configuration with SimpleLogger</a>.
</p>

</div>
<!-- SECTION "Frameworks for Java SE/OSGi, JUnit Test Suite" [367-] -->

<div class="level1">

<p>

Especially during debugging and testing your system, it is important that blocks log any relevant events. For that, you should use the provided logging methods, rather than <em>System.out</em> or <em>System.err</em>. 
</p>

<p>

Logging is based upon <a href="http://www.slf4j.org" class="urlextern" title="http://www.slf4j.org"  rel="nofollow">SLF4J</a>. The common superclass for block declares a SLF4J logger object, which you can use. 
</p>
<pre class="code java"><span class="kw1">public</span> <span class="kw4">int</span> getDuration<span class="br0">&#40;</span><span class="br0">&#41;</span> <span class="br0">&#123;</span>
    logger.<span class="me1">debug</span><span class="br0">&#40;</span><span class="st0">&quot;Timer with id {} started with {} milliseconds.&quot;</span>, id, duration<span class="br0">&#41;</span><span class="sy0">;</span>
    ...
<span class="br0">&#125;</span></pre>

<p>
This is the recommended way of logging. The curly braces are replaced by the list of the last arguments. If you are interested why that is a good idea, read the discussion <a href="http://www.slf4j.org/faq.html#logging_performance" class="urlextern" title="http://www.slf4j.org/faq.html#logging_performance"  rel="nofollow">here</a>. Alternatively, the block superclass declares some simple methods for logging on different levels:
</p>
<ul>
<li class="level1"><div class="li"> logError(String m)</div>
</li>
<li class="level1"><div class="li"> logWarn(String m)</div>
</li>
<li class="level1"><div class="li"> logInfo(String m)</div>
</li>
<li class="level1"><div class="li"> logDebug(String m)</div>
</li>
<li class="level1"><div class="li"> logTrace(String m)</div>
</li>
</ul>
<pre class="code java"><span class="kw1">public</span> <span class="kw4">int</span> getDuration<span class="br0">&#40;</span><span class="br0">&#41;</span> <span class="br0">&#123;</span>
    logDebug<span class="br0">&#40;</span><span class="st0">&quot;Timer started with &quot;</span> <span class="sy0">+</span> duration <span class="sy0">+</span> <span class="st0">&quot; milliseconds.&quot;</span><span class="br0">&#41;</span><span class="sy0">;</span>
    ...
<span class="br0">&#125;</span></pre>

</div>

<h4><a name="log_level_error" id="log_level_error">Log Level ERROR</a></h4>
<div class="level4">

<p>

This level should only be used for recording a failure that prevents the system from starting or
running, i.e. the system is completely unusable. Error messages record that something went wrong, i.e. some sort of failure occurred and the system was either not able to recover or it was able to recover but at the expense of losing information or failing to honor a request.
</p>

<p>
It is crucial that:
</p>
<ul>
<li class="level1"><div class="li"> these get logged</div>
</li>
<li class="level1"><div class="li"> sufficient information is provided to identify the cause of the problem</div>
</li>
<li class="level1"><div class="li"> logging is done in a standard way (to allow automatic monitoring)</div>
</li>
</ul>

<p>
For example, if the error is caused by a configuration failure, the configuration file name should
be provided, as well as the property causing the problem.
</p>

</div>

<h4><a name="log_level_warn" id="log_level_warn">Log Level WARN</a></h4>
<div class="level4">

<p>

A WARN message records that something in the system was not as expected. It is not an error,
i.e. it is not preventing correct operation of the system or any part of it, but it is still an indicator
that something is wrong with the system that the operator should be aware of, and may wish to
investigate. This level may be used for errors in user-supplied information.
</p>

<p>
For example, a configuration file was downloaded (and it was readable), but it did not contain any entries, which may be unusual for this application.
</p>

</div>

<h4><a name="log_level_info" id="log_level_info">Log Level INFO</a></h4>
<div class="level4">

<p>

INFO messages are intended to show what’s going on in the system, at a broad level. INFO
messages do not indicate that something is wrong (use WARN or ERROR for that), and the system
should be able to run at full speed in production with INFO level logging.
</p>

<p>
The following types of message are appropriate at INFO level:
</p>
<ul>
<li class="level1"><div class="li"> Item / Component successfully initialized</div>
</li>
<li class="level1"><div class="li"> Transaction started, including some data about what kind of operation and parameters</div>
</li>
<li class="level1"><div class="li"> Transaction completed, including some data about what kind of operation and parameters</div>
</li>
</ul>

</div>

<h4><a name="log_level_debug" id="log_level_debug">Log Level DEBUG</a></h4>
<div class="level4">

<p>

DEBUG messages are intended to help isolating a problem in a running system, by showing the code
that is executed, and the context information used during that execution. In many cases, it is that
context information that is most important, so try to make this information as useful as possible.
</p>

<p>
The following types of message are appropriate at DEBUG level:
</p>
<ul>
<li class="level1"><div class="li"> Entering a block/method/class with parameter</div>
</li>
<li class="level1"><div class="li"> Leaving a block/method/class with its return value</div>
</li>
<li class="level1"><div class="li"> Description of an action being taken (with context information)</div>
</li>
<li class="level1"><div class="li"> Description of calculated values or made decisions (with context information)</div>
</li>
</ul>

<p>

Note that DEBUG messages are intended to be used for debugging in production systems, so they must be
written for public consumption. Avoid any messages in a non-standard format.
</p>

<p>
If a DEBUG message is expensive to generate, you should guard it with a logger.isDebugEnabled()
if check. Just make sure that nothing that happens inside that if statement is required for normal system
operation.
</p>

</div>

<h4><a name="log_level_trace" id="log_level_trace">Log Level TRACE</a></h4>
<div class="level4">

<p>

Trace messages are developer only and should be removed from code before going into production
</p>

</div>

<h4><a name="exceptions" id="exceptions">Exceptions</a></h4>
<div class="level4">

<p>

Ideally, an exception should only be logged by the code that handles the exception. Code that merely
translates the exception should do no logging.

</p>

</div>
