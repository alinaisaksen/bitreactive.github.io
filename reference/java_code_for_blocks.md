---
title: Java Code for Blocks
layout: reference
---


<h1><a name="java_classes_for_building_blocks" id="java_classes_for_building_blocks">Java Classes for Building Blocks</a></h1>
<div class="level1">

<p>

Building blocks, except shallow blocks, are accompanied by Java classes. These Java classes contain the code for the operations and variables declared in the block.
</p>

<p>
If Java code depends on other libraries, <a href="/doc/java_libraries" class="wikilink1" title="doc:java_libraries">bind them to the building block</a>.
</p>

</div>
<!-- SECTION "Java Classes for Building Blocks" [1-308] -->
<h2><a name="extension_and_implementation_of_interfaces" id="extension_and_implementation_of_interfaces">Extension and Implementation of Interfaces</a></h2>
<div class="level2">

<p>
The Java class for a building block may, just as any other Java class, extend a base class and implement different interfaces. We recommend the following:
</p>
<ul>
<li class="level1"><div class="li"> <strong>Only extend the recommended building block classes</strong>, such as no.ntnu.item.arctis.runtime.Block. This is the default for a number of templates. Blocks specialized for certain platforms may extend other classes. These classes offer access to the blockID of a block.</div>
</li>
<li class="level1"><div class="li"> If for some reason you must extend another class for the building block, implement interface IArctisBuildingBlock to obtain the blockID. Since the generated runtime creates the class, you may not declare any constructors manually. (The runtime either uses the default constructor or the one generated which sets all the instance parameters.)</div>
</li>
<li class="level1"><div class="li"> Do not implement interfaces in the block class that can be realized by anonymous classes. This is generally considered bad programming practice. For instance, instead of making a block that contains a UI list implement a selection listener interface, such a selection listener should be contributed by an extra class or by an anonymous class declared within a method.</div>
</li>
</ul>

</div>
<!-- SECTION "Extension and Implementation of Interfaces" [309-1511] -->
<h2><a name="constructor" id="constructor">Constructor</a></h2>
<div class="level2">

<p>
The constructor for a building block Java class is created by the <acronym title="Software Development Kit">SDK</acronym> automatically, if necessary. This constructor is used for example to initialize parameters for the block. 
</p>

<p>
<strong>You should not edit the Java constructor of a building block</strong>, since it is generated automatically to keep it in sync with the instance parameters of the building block. A good place to initialize variables is a call operation action (Java method) that is called when the block is started, or within the declaration of the variables.

</p>

</div>
<!-- SECTION "Constructor" [1512-] -->