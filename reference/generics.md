---
title: Generics
layout: reference
---


<h1><a name="generics" id="generics">Generics</a></h1>
<div class="level1">

<p>

Building blocks can make use of Java Generics to be adaptable to a certain type. For instance, the Reactive Buffer block works on any type of objects that can be buffered. If you instantiate a reactive buffer, its pins <em>add</em> and <em>out</em> refer to the type java.lang.Object:
</p>

<p>
<a href="/_detail/doc/generics-ori.jpg?id=doc%3Ajava_generics" class="media" title="doc:generics-ori.jpg"><img src="/_media/doc/generics-ori.jpg" class="media" alt="" /></a>
</p>

<p>
In the given case, we want to work with objects of type SMS instead. Luckily, the Reactive Buffer block may be adapted to that type. From the context menu, select “Parameters and Generics…” and adjust the type.
The result is shown below. Pins <em>add</em> and <em>out</em> refer now to the type SMS.
</p>

<p>
<a href="/_detail/doc/generics-changed.jpg?id=doc%3Ajava_generics" class="media" title="doc:generics-changed.jpg"><img src="/_media/doc/generics-changed.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Generics" [1-653] -->
<h2><a name="declaring_generic_types" id="declaring_generic_types">Declaring Generic Types</a></h2>
<div class="level2">

<p>

To declare generic types, add the declarations into the class signature like you would normally do in Java, and use them like any type within the building block. 
</p>

<p>
<a href="/_detail/doc/generics.jpg?id=doc%3Ajava_generics" class="media" title="doc:generics.jpg"><img src="/_media/doc/generics.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Declaring Generic Types" [654-] -->