---
title: Editing Contracts
layout: reference
---


<h1><a name="editing_contracts" id="external_interfaces_2editing">Editing Contracts</a></h1>
<div class="level1">

<p>

In the <a href="/doc/the_arctis_editor" class="wikilink1" title="doc:the_arctis_editor">Blocks Editor</a>, you can create and edit the ESM of a building block on the page called <strong><em>External</em></strong>.
This page contains a <a href="/doc/esm_basic#tabular_form" class="wikilink1" title="doc:esm_basic">transition table</a>, displaying source and target states, and the parameter nodes that are involved in an ESM transition.
</p>

</div>
<!-- SECTION "External Interfaces 2: Editing" [1-355] -->
<h2><a name="automatic_generation_of_simple_esms" id="automatic_generation_of_simple_esms">Automatic Generation of Simple ESMs</a></h2>
<div class="level2">

<p>

In some cases, building blocks are so simple that the <acronym title="Software Development Kit">SDK</acronym> can “guess” the right ESM. For this action, select <em>Generate ESM…</em> on the transition table. 
</p>

<p>
<a href="/_detail/doc/esm-generation.png?id=doc%3Aesm_creation" class="media" title="doc:esm-generation.png"><img src="/_media/doc/esm-generation.png" class="media" alt="" /></a>
</p>

<p>
The resulting ESM always has one state named <em>active</em> and a transition for each parameter node. For some cases, this may already be the ESM that you want to have. In all other cases, this can be a startting point that can be manually extended. 
</p>

</div>
<!-- SECTION "Automatic Generation of Simple ESMs" [356-839] -->
<h2><a name="esm_transitions" id="esm_transitions">ESM Transitions</a></h2>
<div class="level2">

<p>
When you add or edit a transition, you&#039;ll get the window depicted in the following figure.
</p>

<p>
<a href="/_detail/doc/esm-window.jpg?id=doc%3Aesm_creation" class="media" title="doc:esm-window.jpg"><img src="/_media/doc/esm-window.jpg" class="media" alt="" /></a>

</p>
<ol>
<li class="level1"><div class="li"> <strong>Source states</strong> can be an initial state or a normal state. There must be exactly one initial state. States can have names that help to understand the states of the building block.</div>
</li>
<li class="level1"><div class="li"> <strong>Target states</strong> can be normal states or final states. Since all building blocks need some form of termination, at least one final state is needed.</div>
</li>
<li class="level1"><div class="li"> An ESM transition refers to all <strong>parameter nodes</strong> that are passed by a token within the activity step that the ESM transition describes. </div>
</li>
<li class="level1"><div class="li"> In most transitions that contain more than one parameter node, the sequence of the nodes is important. Use the <strong>Move Up</strong> and <strong>Move Down</strong> buttons to sort the nodes.</div>
</li>
</ol>

<p>

The labels of the ESM transitions are computed <strong>automatically</strong>, based on which parameters are part of the transition and in which sequence they are sorted. A label is a sequence of groups of parameters. A group either consists only of input or output parameters.

</p>
<ul>
<li class="level1"><div class="li"> The semicolon ”;” separates different groups of parameters. </div>
</li>
<li class="level1"><div class="li"> The plus ”+” separates parameters within the same group.</div>
</li>
<li class="level1"><div class="li"> The sequence of groups alternates between input and output groups.</div>
</li>
<li class="level1"><div class="li"> The slash ”/” is written after the first group of input parameters, or before the first group of output parameters.</div>
</li>
</ul>

<p>

Intuitively, the slash is placed to that spontaneous transitions, which are triggered from within a building block are written with a slash as prefix.
</p>

</div>
<!-- SECTION "ESM Transitions" [840-2378] -->
<h2><a name="creating_esms" id="creating_esms">Creating ESMs</a></h2>
<div class="level2">

<p>

It is necessary to understand ESMs and <a href="/doc/semantics" class="wikilink1" title="doc:semantics">activity steps</a> in order to correctly <a href="/doc/using_building_blocks" class="wikilink1" title="doc:using_building_blocks">use</a> a building block and all the more to create the ESM of a building block.
</p>

<p>
A general guideline to create an ESM of a block manually is as follows.

</p>
<ol>
<li class="level1"><div class="li"> It is often the case that the author of the block already have an idea in mind how the block should work.</div>
</li>
<li class="level1"><div class="li"> Identify the <a href="/doc/semantics" class="wikilink1" title="doc:semantics">activity steps</a> in the activity diagram, also token markings before and after a step.</div>
</li>
<li class="level1"><div class="li"> Pay attention to the steps that contain parameter nodes and also the types of parameter nodes.</div>
</li>
<li class="level1"><div class="li"> Then, create the ESM based on those factors above:</div>
<ul>
<li class="level2"><div class="li"> An initial transition is related to an activity step that includes a starting parameter node.</div>
</li>
<li class="level2"><div class="li"> Activity steps that include a terminating node or an alternative terminating node form transitions to a final state.</div>
</li>
<li class="level2"><div class="li"> ESM states correspond to token places inside the block between the activity steps.</div>
</li>
<li class="level2"><div class="li"> ESM transitions refer activity steps containing one or more parameter nodes.</div>
</li>
</ul>
</li>
</ol>

<p>

You can check whether the block and its corresponding ESM are consistent by using the <a href="/doc/analysis" class="wikilink1" title="doc:analysis">analyzer</a> tool. Moreover, make sure that the block behaves as intended with the <a href="/doc/animation" class="wikilink1" title="doc:animation">animation</a> tool.
</p>

<p>
An example of creating the ESM of a block is described <a href="/doc/esm_example" class="wikilink1" title="doc:esm_example">here</a>.
</p>

</div>
<!-- SECTION "Creating ESMs" [2379-3760] -->
<h2><a name="internal_activity_steps" id="internal_activity_steps">Internal Activity Steps</a></h2>
<div class="level2">

<p>

There are activity steps in a <a href="/doc/building_blocks#local_blocks" class="wikilink1" title="doc:building_blocks">local block</a> that <strong>include neither input nor output parameters</strong>. Intuitively, for these internal steps we do not create ESM transitions.
</p>

</div>
<!-- SECTION "Internal Activity Steps" [3761-4003] -->
<h2><a name="esm_of_a_composed_block" id="esm_of_a_composed_block">ESM of a Composed Block</a></h2>
<div class="level2">

<p>

A building block can be composed of inner blocks. Creating an ESM of this kind of block is pretty much the same as the guideline described above. However, in this case you also need to consider the inner blocks&#039; ESMs.
</p>

</div>
<!-- SECTION "ESM of a Composed Block" [4004-] -->