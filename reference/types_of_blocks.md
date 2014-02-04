---
title: Activity Nodes
layout: reference
---


<h1><a name="overview" id="overview">Overview</a></h1>
<div class="level1">

<p>

Applications and systems are constructed from reactive blocks. A reactive block is a combination of diagrams and Java 
code, which are tightly connected.
</p>
<ul>
<li class="level1"><div class="li"> An <strong><a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">external state machine (ESM)</a></strong> is the contract between a building block and the enclosing application. It describes in which order the input and output parameters of a building block can be used.</div>
</li>
<li class="level1"><div class="li"> An <strong><a href="/doc/activity_nodes" class="wikilink1" title="doc:activity_nodes">activity diagram</a></strong> is used to describe the internal behavior of a building block.</div>
</li>
<li class="level1"><div class="li"> <strong><a href="/doc/java_operations" class="wikilink1" title="doc:java_operations">Java methods</a></strong> are used to describe the details of operations in an activity diagram.</div>
</li>
</ul>

<p>

There are several types of building blocks.

</p>
<table class="inline">
	<tr class="row0">
		<td class="col0 leftalign">           </td><th class="col1"> Internal Behavior </th><th class="col2"> External Behavior <br/>
(ESM) </th><th class="col3"> Java Code <br/>
(Operations) </th>
	</tr>
	<tr class="row1">
		<th class="col0 leftalign"> Local Block       </th><td class="col1 centeralign">  Activity        </td><td class="col2 centeralign">  yes  </td><td class="col3 centeralign">  yes  </td>
	</tr>
	<tr class="row2">
		<th class="col0 leftalign"> System Block            </th><td class="col1 centeralign">  Activity        </td><td class="col2 centeralign">  -     </td><td class="col3 centeralign">  yes  </td>
	</tr>
	<tr class="row3">
		<th class="col0 leftalign"> Shallow Block        </th><td class="col1 centeralign">  -  </td><td class="col2 centeralign">  yes  </td><td class="col3 centeralign">  -  </td>
	</tr>
	<tr class="row4">
		<th class="col0 leftalign"> State Machine Block        </th><td class="col1 centeralign">  State Machine  </td><td class="col2 centeralign">  yes  </td><td class="col3 centeralign">  yes  </td>
	</tr>
</table>

</div>
<!-- SECTION "Overview" [1-1000] -->
<h2><a name="local_blocks" id="local_blocks">Local Blocks</a></h2>
<div class="level2">

<p>

Local blocks describe behavior that is executed on a single component. Most building blocks in an application are of this type. “Local” is relative to the activity diagram: The operations may well invoke code on other machines.
</p>

<p>
The Motion Detector below is an example for a local block. The activity diagram is shown on the left hand-side and its corresponding ESM is on the right.
</p>

<p>
<a href="/_detail/doc/local-block-example.jpg?id=doc%3Abuilding_blocks" class="media" title="doc:local-block-example.jpg"><img src="/_media/doc/local-block-example.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Local Blocks" [1001-1446] -->
<h2><a name="system_blocks" id="system_blocks">System Blocks</a></h2>
<div class="level2">

<p>

A system block specifies an application or system at the highest decomposition level. It does not have any input or output parameters, but initial nodes for start and activity final nodes for termination. To implement applications or systems, you need this type of block as top-level element.
</p>

<p>
<a href="/_detail/tutorial/cosm-trigger-9.jpg?id=doc%3Abuilding_blocks" class="media" title="tutorial:cosm-trigger-9.jpg"><img src="/_media/tutorial/cosm-trigger-9.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "System Blocks" [1447-1802] -->
<h2><a name="shallow_blocks" id="shallow_blocks">Shallow Blocks</a></h2>
<div class="level2">

<p>

A shallow block is used to coordinate flows in an activity diagram in a more powerful way than what the activity nodes like joins allow. Formally they behave like state machines. In contrast to local blocks, they consist of an ESM and an activity that only has parameter nodes.
</p>

<p>
Below is an example.
</p>

<p>
<a href="/_detail/doc/block-shallow-example2.png?id=doc%3Abuilding_blocks" class="media" title="doc:block-shallow-example2.png"><img src="/_media/doc/block-shallow-example2.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Shallow Blocks" [1803-2169] -->
<h2><a name="state_machine_blocks" id="state_machine_blocks">State Machine Blocks</a></h2>
<div class="level2">

<p>

State Machine Blocks enable you to describe the internal behavior of a block as State Machine. This kind of block does not have an Activity Diagram, but a table defining the State Machine Behavior. State Machine Blocks have an ESM, as local blocks do, to be able to integrate them properly. However, it is derived automatically from the (consistent) State Machine Behavior. Java methods implement guards and operations used by the State Machine.
</p>

<p>
<a href="/_detail/doc/rbminimal.png?id=doc%3Abuilding_blocks" class="media" title="doc:rbminimal.png"><img src="/_media/doc/rbminimal.png" class="media" alt="" /></a>

</p>

</div>
<!-- SECTION "State Machine Blocks" [2170-] -->