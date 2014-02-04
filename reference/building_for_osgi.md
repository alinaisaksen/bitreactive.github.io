---
title: Building for OSGi
layout: reference
---


<h1><a name="osgi_bundles" id="osgi_bundles">Building for OSGi</a></h1>
<div class="level1">

</div>
<!-- SECTION "Building for OSGi" [1-29] -->
<h2><a name="creating_an_osgi_bundle" id="creating_an_osgi_bundle">Creating an OSGi Bundle</a></h2>
<div class="level2">

<p>

When implementing your application, simply select <em>Java OSGi Bundle</em> as platform. As result, you will obtain a generated project that contains a JAR file (the OSGi bundle) which is ready for deployment. 
</p>

</div>
<!-- SECTION "Creating an OSGi Bundle" [30-273] -->
<h2><a name="starting_an_osgi_bundle" id="starting_an_osgi_bundle">Starting an OSGi Bundle</a></h2>
<div class="level2">

<p>

There are numerous OSGi frameworks, for instance:
</p>
<ul>
<li class="level1"><div class="li"> <a href="http://felix.apache.org/site/index.html" class="urlextern" title="http://felix.apache.org/site/index.html"  rel="nofollow"> Apache Felix</a></div>
</li>
<li class="level1"><div class="li"> <a href="http://www.knopflerfish.org/" class="urlextern" title="http://www.knopflerfish.org/"  rel="nofollow"> Knopflerfish OSGi</a></div>
</li>
<li class="level1"><div class="li"> <a href="http://www.eclipse.org/equinox/" class="urlextern" title="http://www.eclipse.org/equinox/"  rel="nofollow"> Equinox</a></div>
</li>
</ul>

<p>
Bundles generated by the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> should run on all of these. In the following, we just picked Equinox to explain how to run an OSGi bundle.
</p>

</div>
<!-- SECTION "Starting an OSGi Bundle" [274-684] -->
<h3><a name="using_equinox_on_the_command_line" id="using_equinox_on_the_command_line">Using Equinox on the Command Line</a></h3>
<div class="level3">

</div>

<h4><a name="install_equinox" id="install_equinox">Install Equinox</a></h4>
<div class="level4">
<ul>
<li class="level1"><div class="li"> Go to <a href="http://download.eclipse.org/equinox/" class="urlextern" title="http://download.eclipse.org/equinox/"  rel="nofollow">http://download.eclipse.org/equinox/</a> </div>
</li>
<li class="level1"><div class="li"> Navigate to version 3.7.2</div>
</li>
<li class="level1"><div class="li"> Download the <em>Framework Only</em> package</div>
</li>
<li class="level1"><div class="li"> You receive a JAR file, for instance org.eclipse.osgi_3.7.2.v20120110-1415.jar</div>
</li>
<li class="level1"><div class="li"> Parallel to the JAR file, create a folder <em>configuration</em></div>
</li>
<li class="level1"><div class="li"> Within this folder, create a file <em>config.ini</em>, with the following content:</div>
</li>
</ul>
<pre class="code">
eclipse.ignoreApp=true 
</pre>

<p>

This prevents Equinox from trying to start as an Eclipse runtime, which would result in error messages.  
</p>

</div>

<h4><a name="start_equinox" id="start_equinox">Start Equinox</a></h4>
<div class="level4">
<ul>
<li class="level1"><div class="li"> In the terminal, go to the directory where you downloaded the framework</div>
</li>
<li class="level1"><div class="li"> Start the framework:</div>
</li>
</ul>
<pre class="code">
java -jar org.eclipse.osgi_3.7.2.v20120110-1415.jar -console
</pre>

<p>

You should now see the OSGi command line:

</p>
<pre class="code">
osgi&gt;
</pre>

<p>

Type <em>ss</em>, and you should see the status of the framework:

</p>
<pre class="code">
osgi&gt; ss

Framework is launched.

id	State       Bundle
0	ACTIVE      org.eclipse.osgi_3.7.0.v20110613

osgi&gt; 
</pre>

</div>

<h4><a name="install_your_bundle" id="install_your_bundle">Install Your Bundle</a></h4>
<div class="level4">

<p>

Now type <em>install file:</em>&#47;&#47;, followed by the path to the bundle you created previously with the <acronym title="Software Development Kit">SDK</acronym>. (Depending on which terminal you are using, it is possible to drag the created bundle into the terminal so its absolute file name is added.)
</p>
<pre class="code">
osgi&gt; install file:///Users/.../com.bitreactive.experiments.osgi.component_1.0.0.jar 
Bundle id is 1

osgi&gt; 
</pre>

<p>

Type again <em>ss</em>, and you should see the status of the framework:
</p>
<pre class="code">
osgi&gt; ss

Framework is launched.

id	State       Bundle
0	ACTIVE      org.eclipse.osgi_3.7.0.v20110613
1	INSTALLED   com.bitreactive.experiments.osgi.component_1.0.0.2012071419

osgi&gt; 
</pre>

<p>

You see that our bundle got a number assigned. This is so you can refer to the bundle within the comments more easily. Our bundle here got id 1. 
</p>

</div>

<h4><a name="start_your_bundle" id="start_your_bundle">Start Your Bundle</a></h4>
<div class="level4">

<p>
To start the bundle, simply type

</p>
<pre class="code">
osgi&gt; start 1

osgi&gt; 
</pre>

<p>

Now the bundle executes its code, just like any other Java application. 

</p>

</div>
<!-- SECTION "Using Equinox on the Command Line" [685-] -->