---
title: Testing with JUnit
layout: reference
---


<h1><a name="testing_libraries_with_junit" id="testing_libraries_with_junit">Testing with JUnit</a></h1>
<div class="level1">

<p>

We recommend to build test cases for each new building block, to ensure that all operations work as intended. 
</p>

<p>
Testing is based on JUnit, a widely used framework for unit testing. You can read more about JUnit testing <a href="http://en.wikipedia.org/wiki/JUnit" class="urlextern" title="http://en.wikipedia.org/wiki/JUnit"  rel="nofollow">here</a>.
</p>

</div>
<!-- SECTION "Testing Libraries with JUnit" [1-310] -->
<h2><a name="create_a_new_test_project" id="create_a_new_test_project">Create a new Test Project</a></h2>
<div class="level2">
<ul>
<li class="level1"><div class="li"> Select File / New / Project…</div>
</li>
<li class="level1"><div class="li"> Select Reactive Blocks / Reactive Blocks Project</div>
</li>
<li class="level1"><div class="li"> Choose the JUnit project setup</div>
</li>
</ul>

<p>

<a href="/_detail/doc/new-test-project2.png?id=doc%3Ajunit" class="media" title="doc:new-test-project2.png"><img src="/_media/doc/new-test-project2.png" class="media" alt="" /></a>
</p>

<p>
Generally, it is a good idea to create a new test project for each library that you want to test. We recommend to use the same qualified name ad the library under test, with <strong>.tests</strong> added. So, for our library <em>org.reactiveblocks.library.foo</em>, we create a test project called <em>org.reactiveblocks.library.foo.tests.</em>
</p>

</div>
<!-- SECTION "Create a new Test Project" [311-829] -->
<h2><a name="create_a_new_test_case" id="create_a_new_test_case">Create a new Test Case</a></h2>
<div class="level2">

<p>

Within the test project, create a new system building block. Each system provides one test run, and it&#039;s okay to have many systems and many tests within a test project. 
</p>

<p>
Usually, each test system focuses on a single block from a library to test. In the example, we have created <em>Foo Test 1</em> to test the block <em>Foo</em> of our library.
</p>

<p>
<a href="/_detail/doc/new-test-project.png?id=doc%3Ajunit" class="media" title="doc:new-test-project.png"><img src="/_media/doc/new-test-project.png" class="media" alt="" /></a>
</p>

<p>

A test usually starts by preparing some data. Here we do that in the simple operation <em>prepare</em>. However, you can involve any other building blocks to prepare the system for testing.
</p>

<p>
The verdict of the test is written in operations as well. Here we have a simple setup: Whenever the block answers via pin <em>bad</em>, the test should fail. Therefore, the method <em>failed</em> is pretty simple:

</p>
<pre class="code">  import org.junit.Assert;
  ...
  public void testFailed() {
      Assert.fail(&quot;Test failed, too bad!&quot;);
  }</pre>

<p>

The class <strong>Assert</strong> is from JUnit, and is on the classpath because the JUnit libraries were added during the project setup. In addition to the simple method <em>fail</em>, it also contains methods to compare data.
</p>

</div>
<!-- SECTION "Create a new Test Case" [830-1959] -->
<h2><a name="implementing_the_test_case" id="implementing_the_test_case">Implementing the Test Case</a></h2>
<div class="level2">

<p>

To implement all test cases within your test project do the following:
</p>
<ul>
<li class="level1"><div class="li"> Select and Right-click on the project in the Blocks view</div>
</li>
<li class="level1"><div class="li"> Select <em>Implement All (JUnit)</em></div>
</li>
</ul>

<p>

This will implement <em>all</em> test cases within the project, and compile them into a single JUnit test suite that can be executed in one single run.
</p>

<p>
<a href="/_detail/doc/junit-generated-test-case.png?id=doc%3Ajunit" class="media" title="doc:junit-generated-test-case.png"><img src="/_media/doc/junit-generated-test-case.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Implementing the Test Case" [1960-2358] -->
<h2><a name="ignoring_a_test_case" id="ignoring_a_test_case">Ignoring a Test Case</a></h2>
<div class="level2">

<p>

If you want that certain test cases from a project are excluded from the test suite, just tag the corresponding block with the tag <em>ignore</em> within the Overview page of that block.
</p>

<p>
<a href="/_detail/doc/junit_tag_ignore_small.png?id=doc%3Ajunit" class="media" title="doc:junit_tag_ignore_small.png"><img src="/_media/doc/junit_tag_ignore_small.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Ignoring a Test Case" [2359-2613] -->
<h2><a name="running_the_test_suite" id="running_the_test_suite">Running the Test Suite</a></h2>
<div class="level2">
<ul>
<li class="level1"><div class="li"> Right-click the generated test suite project</div>
</li>
<li class="level1"><div class="li"> Select <em>Run as / JUnit Test</em></div>
</li>
</ul>

<p>

As a result, the JUnit view of Eclipse shows up, executes the tests and shows the test results.
</p>

<p>
<a href="/_detail/doc/junit-test-view.png?id=doc%3Ajunit" class="media" title="doc:junit-test-view.png"><img src="/_media/doc/junit-test-view.png" class="media" alt="" /></a>
</p>

<p>

In the example, two of the test cases failed. In these case, the message provided with the verdict method will show up, and helps you to locate the error.
</p>

</div>
<!-- SECTION "Running the Test Suite" [2614-] -->


<h1><a name="build_junit_projects" id="build_junit_projects">Build JUnit Projects</a></h1>
<div class="level1">

<p>
A JUnit test project (<a href="/_detail/doc/junit.png?id=doc%3Abuild_junit" class="media" title="doc:junit.png"><img src="/_media/doc/junit.png" class="media" alt="" /></a>) typically contains several test blocks. For this type of project you can build all test systems with one action. Choose <em>Build</em> from the context menu of such project in the Block view. Then, select <em>Build JUnit Test Project</em> to start the build process.
</p>

<p>
<a href="/_detail/doc/build-junit2.jpg?id=doc%3Abuild_junit" class="media" title="doc:build-junit2.jpg"><img src="/_media/doc/build-junit2.jpg" class="media" alt="" /></a>
</p>

<p>
You can also build all test blocks in your workspace with a single click. For this, choose option <em>Build all JUnit Test Projects</em>. This option is only shown when you have several JUnit projects in your workspace.
</p>

<p>
Similar to building a system, you will be prompted with a dialog that enables you to change the logging framework and level, the generated project name, etc. All executable code is placed in one project that is highlighted when the build process is done.
</p>

</div>
