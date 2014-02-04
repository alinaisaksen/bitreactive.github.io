---
title: Java Methods
layout: reference
---


<h1><a name="java_methods" id="java_methods">Java Methods</a></h1>
<div class="level1">

<p>

Building blocks can contain <strong>operations</strong>. Their content is described by Java methods. The behavior of the building block determines when and in which sequence Java methods are called, and passes parameters to them.
Java methods are edited in the usual context of JDT within Eclipse, which means that everything you know about Java programming in Eclipse applies also for Java operations of building blocks.
</p>
<ul>
<li class="level1"><div class="li"> <strong>Java methods are never allowed to block or wait.</strong> This rule ensures that applications can be executed efficiently and stay responsive. If some code has to wait for an external response (for instance an <acronym title="Hyper Text Transfer Protocol">HTTP</acronym> request) there exist notification patterns to decouple the behavior.</div>
</li>
<li class="level1"><div class="li"><strong>Exceptions must be caught within the methods.</strong> Java methods that represent operations must not throw any exceptions. This means you have to think of all exceptions that may happen and handle them appropriately. </div>
</li>
<li class="level1"><div class="li"> Since the operations in the graphical model refer to the Java methods <em>by name</em>, <strong>only one Java method with a certain name may exist</strong>, although Java allows several methods with the same name as long as they have a different signature. </div>
</li>
</ul>

</div>
<!-- SECTION "Java Methods" [1-1187] -->
<h2><a name="editing_java_methods" id="editing_java_methods">Editing Java Methods</a></h2>
<div class="level2">
<ul>
<li class="level1"><div class="li"> Select the operation from the context menu</div>
</li>
</ul>

<p>

<a href="/_detail/doc/add-operation.jpg?id=doc%3Ajava_operations" class="media" title="doc:add-operation.jpg"><img src="/_media/doc/add-operation.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> click on a partition to create a new operation in that partition</div>
</li>
<li class="level1"><div class="li"> in the editor, create a new one by assigning a new name</div>
</li>
</ul>

<p>

<a href="/_detail/doc/new-operation.jpg?id=doc%3Ajava_operations" class="media" title="doc:new-operation.jpg"><img src="/_media/doc/new-operation.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> double-click on the operation, and the corresponding Java method is revealed</div>
</li>
</ul>

<p>

<a href="/_detail/doc/operation.jpg?id=doc%3Ajava_operations" class="media" title="doc:operation.jpg"><img src="/_media/doc/operation.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> now add any parameters by editing the signature of the method, and add a return type, if needed</div>
</li>
</ul>

<p>

<a href="/_detail/doc/java-operation-editing.png?id=doc%3Ajava_operations" class="media" title="doc:java-operation-editing.png"><img src="/_media/doc/java-operation-editing.png" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> once you switch to the behavior page with the activity, the operation is updated with input and output pins</div>
</li>
</ul>

<p>
<a href="/_detail/doc/java-operation-page-switch.png?id=doc%3Ajava_operations" class="media" title="doc:java-operation-page-switch.png"><img src="/_media/doc/java-operation-page-switch.png" class="media" alt="" /></a>
<a href="/_detail/doc/java-operation-pins.png?id=doc%3Ajava_operations" class="media" title="doc:java-operation-pins.png"><img src="/_media/doc/java-operation-pins.png" class="media" alt="" /></a>
</p>

<p>
Java methods referred to by the building block need to be public.
You may also include private methods in the class for the building block, but these are invisible for the behavior of the block.
</p>

<p>

Note an operation to be added to a block can also be selected from the context menu, if it is already available in the *.java page.
</p>

</div>
<!-- SECTION "Editing Java Methods" [1188-2221] -->
<h2><a name="renaming_java_methods" id="renaming_java_methods">Renaming Java Methods</a></h2>
<div class="level2">

<p>

Currently, there is no automated refactoring support available to rename a Java methods, but you can do the following:
</p>
<ul>
<li class="level1"><div class="li"> Rename the Java method in the Java source code</div>
</li>
<li class="level1"><div class="li"> Switch to the behavior view of the building block</div>
</li>
<li class="level1"><div class="li"> Open the context menu on the operation pointing to the Java method</div>
</li>
<li class="level1"><div class="li"> Select “Operation Code”, and point to the new name of the Java method</div>
</li>
</ul>

</div>
<!-- SECTION "Renaming Java Methods" [2222-] -->