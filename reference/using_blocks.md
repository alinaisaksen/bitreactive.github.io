---
title: Using Blocks
layout: reference
---


<h1><a name="connecting_building_blocks" id="connecting_building_blocks">Connecting Building Blocks</a></h1>
<div class="level1">

<p>

A building block can be composed from other building blocks from libraries or your own projects. In contrast to programming approach, with the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> developers reuse not only code, but also the <a href="/doc/activity_nodes" class="wikilink1" title="doc:activity_nodes">activity diagram</a> describing the behavior of this block and its corresponding external interface <a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">ESM</a>. 
</p>

<p>
In order to compose building blocks, first you need to instantiate them and then wire them by connecting their pins with control or object <a href="/doc/control_and_object_flows" class="wikilink1" title="doc:control_and_object_flows">flows</a>.
</p>

</div>
<!-- SECTION "Connecting Building Blocks" [1-575] -->
<h2><a name="instantiating_blocks" id="instantiating_blocks">Instantiating Blocks</a></h2>
<div class="level2">

<p>

To instantiate a building block, you can drag the block from the Blocks view to the activity diagram on the behavior page of the Blocks Editor as illustrated with an arrow labelled with <strong>(1)</strong> in the figure below.
</p>

<p>
<a href="/_detail/doc/using-bb4.jpg?id=doc%3Ausing_building_blocks" class="media" title="doc:using-bb4.jpg"><img src="/_media/doc/using-bb4.jpg" class="media" alt="" /></a>
</p>

<p>

In the Blocks Editor then you will get a blue block <strong>(2)</strong> with pins on its edges.
</p>

<p>
The block is an instance that refers to the actual building block. You can consider a block instance and its referred block like an object and its class in the object-oriented concept. Double-click a block instance to view its full specification. However, looking at its full specification is NOT necessary to use a block. Since it is an instance, any modification should be done on the actual specification of the building block. This means that you cannot, for example, add or delete pins (see the next section) on a block instance.
</p>

<p>
A reactive block is a software module that usually encapsulates more details then you need to know when using this block. The usage of a reactive block depends on understanding its <a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">ESM</a>  and connecting its pins appropriately.
</p>

<p>
From the context menu of a block instance, you can:
</p>
<ul>
<li class="level1"><div class="li"> see a brief information about the block from action <em>"Show info..."</em></div>
</li>
<li class="level1"><div class="li"> open the block&#039;s <a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">ESM</a> from action <em>"Show ESM"</em></div>
</li>
<li class="level1"><div class="li"> refer to another block from action <em>"Set Building Block..."</em></div>
</li>
<li class="level1"><div class="li"> set <a href="/doc/instance_parameters_for_building_blocks" class="wikilink1" title="doc:instance_parameters_for_building_blocks">instance parameters</a> and <a href="/doc/java_generics" class="wikilink1" title="doc:java_generics">generics</a> if the block specifies any from action <em>“Parameters and Generics”</em></div>
</li>
</ul>

<p>

Executing action <em>"Match with Original Block"�</em> means that the instance is synchronized with its corresponding specification. This action needs to be taken when the original specification is changed.
</p>

</div>
<!-- SECTION "Instantiating Blocks" [576-2366] -->
<h2><a name="pins" id="pins">Pins</a></h2>
<div class="level2">

<p>

The <strong>pins</strong> on a block instance are used to <a href="/doc/control_and_object_flows" class="wikilink1" title="doc:control_and_object_flows">connect</a> the block with other modeling elements. 
</p>

<p>
You will often see several different types of pin.
These are just intended to help you use the block instance.
Sometimes, the name of the pin gives you a good idea on how to compose the instance.
</p>

<p>
An example of a block instance with its pins is depicted in the figure below.
</p>

<p>
<a href="/_detail/doc/pins.jpg?id=doc%3Ausing_building_blocks" class="media" title="doc:pins.jpg"><img src="/_media/doc/pins.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Starting and terminating pins indicates start and termination of a block respectively. These pins have white background. They are used to control the life cycle of a block instance.</div>
</li>
<li class="level1"><div class="li"> Streaming input and output are used to interact with a block when it is active. These pins have black background.</div>
</li>
<li class="level1"><div class="li"> Double frame around white pins indicate alternatives. It is usually used by terminating pins. There are alternative starting pins too, however they are much seldom.</div>
</li>
</ul>

<p>

All types of pin can be used with all types of flows. So no matter if a pin is a starting or terminating or streaming pin, it can be connected using a control or a object flow. Note that you do not need to use all pins. There may be for example an output streaming pin which provides data you are not interested in. In that case you may leave this pin just unconnected.
</p>

<p>
You can move a pin along an edge with the arrow keys → and ←. The orientation of a pin can be changed with key <em>“r”</em> for rotate or from the context menu.
</p>

</div>
<!-- SECTION "Pins" [2367-3813] -->
<h2><a name="the_interface_contract_of_a_block_instance" id="the_interface_contract_of_a_block_instance">The Interface Contract of a Block Instance</a></h2>
<div class="level2">

<p>

In order to use a block instance correctly, you need to understand its behavior interface contract as described <a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">here</a>.
</p>

<p>
Use the <a href="/doc/analysis" class="wikilink1" title="doc:analysis">analyzer</a> and <a href="/doc/animation" class="wikilink1" title="doc:animation">animator</a> tools to check whether the block instance is correctly integrated into an enclosing block.

</p>

</div>
<!-- SECTION "The Interface Contract of a Block Instance" [3814-] -->