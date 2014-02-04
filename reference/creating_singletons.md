---
title: Creating Singletons
layout: reference
---


<h1><a name="creating_singletons" id="creating_singletons">Creating Singletons</a></h1>
<div class="level1">

<p>

As with singletons in programming, A singleton block is useful when you need to make a resource that is only accessible once available from several places in the system.
</p>

<p>
Singletons are special blocks, which exist with exactly one instance in a system, no matter how often they occur in a specification. This means that, unless as with all other blocks, all occurrences of a singleton within a system refer to the same instance.
</p>

</div>
<!-- SECTION "Creating Singletons" [1-465] -->
<h2><a name="creating_a_new_singleton" id="creating_a_new_singleton">Creating a New Singleton</a></h2>
<div class="level2">

<p>

There are two ways to create a new singleton:
</p>
<ul>
<li class="level1"><div class="li"> Create a new building block, and select the <em>Singleton</em> template. </div>
</li>
<li class="level1"><div class="li"> Open an existing building block, and select singleton as session pattern on the overview page.</div>
</li>
</ul>

</div>
<!-- SECTION "Creating a New Singleton" [466-723] -->
<h2><a name="start_and_termination" id="start_and_termination">Start and Termination</a></h2>
<div class="level2">
<ul>
<li class="level1"><div class="li"> A singleton does <strong>not</strong> have a starting pin. It is started automatically just before it receives its first parameter.</div>
</li>
<li class="level1"><div class="li"> A singleton is terminated automatically when the system terminates. </div>
</li>
</ul>

</div>
<!-- SECTION "Start and Termination" [724-955] -->
<h2><a name="coordinating_input_and_output" id="coordinating_input_and_output">Coordinating Input and Output</a></h2>
<div class="level2">

<p>

A singleton is used by potentially many clients, all at the same time. This means that a request that comes from a specific client must remember which client it comes from, so that the response can be sent back properly. For this, we use the class <em>SingletonData</em>.

</p>
<ul>
<li class="level1"><div class="li"> All input and output parameters of a singleton must be of type <em>SingletonData</em>. This is a wrapper class that can transport data together with addressing information.</div>
</li>
<li class="level1"><div class="li"> Within the singleton, you usually do not need to create new instances of SingletonData. Only use the instances received from the outside. You can add your response as the data, and it will find its way back to the client where it came from.</div>
</li>
</ul>

</div>
<!-- SECTION "Coordinating Input and Output" [956-] -->