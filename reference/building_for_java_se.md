---
title: Building for Java SE
layout: reference
---


<h1><a name="build_a_system" id="build_a_system">Building for Java SE</a></h1>
<div class="level1">

<p>
From an application (marked as <strong>«system»</strong>) and its contained building blocks you can automatically generate an executable project. Code that you wrote manually within the building blocks is copied into the project, the rest is generated automatically.
</p>

<p>
Note that the result is an Eclipse project, by default marked with a suffix <strong>_exe</strong>. This project is, once generated, completely independent from the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym>.
</p>

</div>
<!-- SECTION "Build a System" [1-462] -->
<h2><a name="starting_the_build_process" id="starting_the_build_process">Starting the Build Process</a></h2>
<div class="level2">

<p>

Open the «system» building block that you want to generate code for and select <em>Build</em> in its context menu. Further, choose <em>Select Build Target Platform…</em> to open a dialog displaying all platform choices, e.g., J2SE, OSGi (see the next section). If the system was build before, you will also see an option to rebuild the system for a specific target platform.
</p>

<p>
<a href="/_detail/doc/build-action-context-menu.jpg?id=doc%3Aimplementing_a_system" class="media" title="doc:build-action-context-menu.jpg"><img src="/_media/doc/build-action-context-menu.jpg" class="media" alt="" /></a>
</p>

<p>
Another way to generate executable code is from the context menu of a system block listed in the Block view. You will find the same build menu as above.
</p>

<p>
<a href="/_detail/doc/build-action-2.jpg?id=doc%3Aimplementing_a_system" class="media" title="doc:build-action-2.jpg"><img src="/_media/doc/build-action-2.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Starting the Build Process" [463-1097] -->
<h2><a name="deployment" id="deployment">Deployment</a></h2>
<div class="level2">

<p>

You need to be online and signed in in order to implement a system. If you haven&#039;t done so, you will be prompt to login.
</p>

<p>
Thereafter, a dialog will ask which code generator to be used to realized the system.
</p>

<p>
<a href="/_detail/doc/platform-selection-2.jpg?id=doc%3Aimplementing_a_system" class="media" title="doc:platform-selection-2.jpg"><img src="/_media/doc/platform-selection-2.jpg" class="media" alt="" /></a>
</p>

<p>
In the next dialog you can choose the logging framework and level you want to use and also change the project name of the generated system. Libraries that are used in the building block can be copied as jar-files or extracted so that you get also Java codes in the generated system.
</p>

<p>
<a href="/_detail/doc/build-parameter.jpg?id=doc%3Aimplementing_a_system" class="media" title="doc:build-parameter.jpg"><img src="/_media/doc/build-parameter.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Deployment" [1098-1683] -->
<h2><a name="the_result" id="the_result">The Result</a></h2>
<div class="level2">

<p>
An executable project is generated automatically. You can find it highlighted in the Java Package Explorer. This highlight will disappear after some time.
</p>

<p>
<a href="/_detail/doc/implement-result.jpg?id=doc%3Aimplementing_a_system" class="media" title="doc:implement-result.jpg"><img src="/_media/doc/implement-result.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "The Result" [1684-1895] -->
<h2><a name="running_an_executable_project" id="running_an_executable_project">Running an Executable Project</a></h2>
<div class="level2">

<p>
You can run the generated project by selecting <em>Run As | Java Application</em> from the context menu of the project.
</p>

<p>
If the project contains several Java applications (classes that contain the <code>public static void main(String[] args)</code> method), then a window like the following will show up.
</p>

<p>
<a href="/_detail/doc/run-app.jpg?id=doc%3Aimplementing_a_system" class="media" title="doc:run-app.jpg"><img src="/_media/doc/run-app.jpg" class="media" alt="" /></a>
</p>

<p>
Choose the class called <em>“Start”</em> that is located in the project where you store your system block.
</p>

</div>
<!-- SECTION "Running an Executable Project" [1896-2355] -->
<h2><a name="troubleshooting" id="troubleshooting">Troubleshooting</a></h2>
<div class="level2">

</div>
<!-- SECTION "Troubleshooting" [2356-2384] -->
<h3><a name="projects_cannot_be_deleted" id="projects_cannot_be_deleted">Projects cannot be deleted</a></h3>
<div class="level3">

<p>
<acronym title="Software Development Kit">SDK</acronym> tries to delete the previously generated project. If your are executing an application, it may be that JAR files are locked by the JVM and deleting these projects fails if you generate them again. 
</p>
<ul>
<li class="level1"><div class="li"> Terminate all running Java applications that you generated and started previously</div>
</li>
<li class="level1"><div class="li"> Try to manually delete the generated project</div>
</li>
<li class="level1"><div class="li"> Implement again </div>
</li>
</ul>

</div>
<!-- SECTION "Projects cannot be deleted" [2385-2781] -->
<h3><a name="java_application_does_not_start" id="java_application_does_not_start">Java application does not start</a></h3>
<div class="level3">

<p>
If the Java application does not start, check if the Start class as described above is generated and OK. It should contain a main() method, which is the entry point for the Java virtual machine. 
</p>

<p>
Check the class path of the project.
</p>
<ul>
<li class="level1"><div class="li"> Right-click the generated _exe project</div>
</li>
<li class="level1"><div class="li"> Select Build Path / Configure Build Path…</div>
</li>
<li class="level1"><div class="li"> Check in all tabs if the classpath is defined correctly. </div>
</li>
</ul>

<p>

If you observe the exception
<code>java.lang.NoClassDefFoundError: …</code>,
something is probably wrong with the JVM that is selected. Go to the classpath and try to select another one.
</p>

</div>
<!-- SECTION "Java application does not start" [2782-] -->