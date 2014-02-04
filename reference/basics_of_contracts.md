---
title: Basics of Contracts
layout: reference
---


<h1><a name="basics_of_contracts" id="external_interfaces_1the_basics">Basics of Contracts</a></h1>
<div class="level1">

<p>

A building block is encapsulated by an <em>external state machine</em> (ESM), that describes the order in which parameters or pins can enter or exit the block. To have an ESM has various benefits:
</p>
<ul>
<li class="level1"><div class="li"> With an ESM, you can understand the coarse behavior of a block, without knowing its internal details.</div>
</li>
<li class="level1"><div class="li"> The analyzer can check if a block is integrated correctly.</div>
</li>
<li class="level1"><div class="li"> You can integrate blocks into your system that aren&#039;t even finished yet, and develop a system top-down.</div>
</li>
</ul>

<p>

The figure bellow shows the block <strong>Speech Buffer</strong> from the outside (external point-of-view) with its corresponding <strong>ESM</strong> on the right hand-side. To open an ESM, you can choose action <em>“Show ESM”</em> from the corresponding block&#039;s context menu.
</p>

<p>
<a href="/_detail/doc/esm-example2.jpg?id=doc%3Aesm_basic" class="media" title="doc:esm-example2.jpg"><img src="/_media/doc/esm-example2.jpg" class="media" alt="" /></a>
</p>

<p>
Intuitively, we first need to initialize the block via pin <em>init</em>. Thereafter, pin <em>speak</em> can be used.
At last, we terminate the block via pin <em>stop</em> and receive a confirmation via pin <em>stopped</em>.
</p>

</div>
<!-- SECTION "External Interfaces 1: The Basics" [1-1001] -->
<h2><a name="states_and_transitions" id="states_and_transitions">States and Transitions</a></h2>
<div class="level2">

<p>

An ESM is specified by a state machine, which consists of <strong>states</strong> and <strong>transitions</strong>. During its life cycle, an ESM typically starts in the initial state, goes through some normal states before it terminates into one of its final states.

</p>
<ul>
<li class="level1"><div class="li"> An <strong>initial state</strong> (<a href="/_detail/doc/initial-state.jpg?id=doc%3Aesm_basic" class="media" title="doc:initial-state.jpg"><img src="/_media/doc/initial-state.jpg" class="media" alt="" /></a>) is the first state of a block. It usually means that the block is <em>switched off</em>, meaning that its internal behavior is not doing anything. Each ESM must have exactly one initial state. </div>
</li>
</ul>
<ul>
<li class="level1"><div class="li"> A normal <strong>state</strong> describes a certain phase in the building block, in which different things may happen. In all normal states, a building block is considered to be <em>active</em>. States with the same name are identical, so the same state may be shown several times within a diagram.</div>
</li>
</ul>
<ul>
<li class="level1"><div class="li"> A <strong>final state</strong> (<a href="/_detail/doc/final-state.jpg?id=doc%3Aesm_basic" class="media" title="doc:final-state.jpg"><img src="/_media/doc/final-state.jpg" class="media" alt="" /></a>) indicates that a block is switched off again, and this state therefore corresponds to the same state as the initial state. An ESM must have at least one final state.</div>
</li>
</ul>

<p>
<a href="/_detail/doc/esm-state.jpg?id=doc%3Aesm_basic" class="media" title="doc:esm-state.jpg"><img src="/_media/doc/esm-state.jpg" class="media" alt="" /></a>
</p>

<p>
As shown in the figure above, the ESM of block Speech Buffered has five states:

</p>
<ul>
<li class="level1"><div class="li"> an <strong>initial</strong> state</div>
</li>
<li class="level1"><div class="li"> state <strong>active</strong></div>
</li>
<li class="level1"><div class="li"> state <strong>stopping</strong></div>
</li>
<li class="level1"><div class="li"> two <strong>final</strong> states</div>
</li>
</ul>

<p>

A <strong>transition</strong> connects a source state to a target state. It is labelled with the pins of a building block. This indicates

</p>
<ul>
<li class="level1"><div class="li"> the incoming flow(s) that can be accepted by the building block</div>
</li>
<li class="level1"><div class="li"> the outgoing flow(s) that must be handled by its environment, i.e., its enclosing block</div>
</li>
</ul>

<p>

The source and target state of a transition can be the same. This is called <strong>self-transition</strong>. In order to improve the readability of ESMs, we include this type of transitions directly below the state name (see state <em>active</em> in the following figure).
</p>

<p>
Transition labels include a slash (<strong>/</strong>) to improve the readability of the ESM transitions. We&#039;ll cover its exact definition later. For now, simply think of the slash of separating the first input pin from the first output pin.
</p>

<p>
<a href="/_detail/doc/esm-transition.jpg?id=doc%3Aesm_basic" class="media" title="doc:esm-transition.jpg"><img src="/_media/doc/esm-transition.jpg" class="media" alt="" /></a>
</p>

<p>

The ESM of block Speech Buffered has five transitions:
</p>
<ol>
<li class="level1"><div class="li"> <strong>init/</strong>: Transition from the initial state to state active. This is the first transition and will activate block Speech Buffered.</div>
</li>
<li class="level1"><div class="li"> <strong>speak/</strong>: Self-transition from and to state active. This indicates that the enclosing block can <em class="u">repeatedly</em> give inputs via pin <em>speak</em>.</div>
</li>
<li class="level1"><div class="li"> <strong>stop/</strong>: Transition from state active to state stopping. Notice that after an incoming flow via pin <em>stop</em>, the block will no longer receive an input via pin <em>speak</em>.</div>
</li>
<li class="level1"><div class="li"> <strong>/stopped</strong>: Transition from state stopping to a final state. A confirmation that the block is terminated is given to the enclosing block.</div>
</li>
<li class="level1"><div class="li"> <strong>stop/stopped</strong>: Transition from state active to a final state. The block receive a stop command from the environment and confirm the termination right away.</div>
</li>
</ol>

<p>

As described above there are two <strong>alternative terminations</strong> for block Speech Buffered:
</p>
<ul>
<li class="level1"><div class="li"> Via transitions “stop/” and then ”/stopped”. This is the case when termination takes time because some internal activities need to be executed before the block can terminate. Here, after receiving “stop” input, the block enters state “stopping” and some time later emits event via pin “stopped” and terminates.</div>
</li>
<li class="level1"><div class="li"> Via transition “stop/stopped”. This is the case when termination can occur immediately.</div>
</li>
</ul>

</div>
<!-- SECTION "States and Transitions" [1002-4358] -->
<h2><a name="parameter_node_and_pin_kinds" id="parameter_node_and_pin_kinds">Parameter Node and Pin Kinds</a></h2>
<div class="level2">

<p>

You may have noticed the different <em>color</em> of the pins on block Speech Buffered. These are also useful to understand the behavior of the block.
</p>
<ul>
<li class="level1"><div class="li"> <strong>White-background input</strong> pin (e.g., pin <em>init</em>) is used to <strong>start</strong> the block. Hence, it is only used to label transitions from the initial state.</div>
</li>
<li class="level1"><div class="li"> <strong>White-background output</strong> pin (e.g., pin <em>stopped</em>) is used to indicate the <strong>termination</strong> of the block. Therefore, it is only used to label transitions towards final states.</div>
</li>
<li class="level1"><div class="li"> <strong>Black-background input</strong> (e.g., pin <em>speak</em>, <em>stop</em>) <strong>and output pins</strong> allow in general flows to enter and respective exit the block when the block is <strong>active</strong>.</div>
</li>
</ul>

</div>
<!-- SECTION "Parameter Node and Pin Kinds" [4359-5063] -->
<h2><a name="tabular_form" id="tabular_form">Tabular Form</a></h2>
<div class="level2">

<p>

Within the tool, ESMs are written in a tabular form.
Every row of the table describes a transition. The columns display the source state of the transition, the transition label (parameter nodes) and the target state of the transition. The tabular form of Speech Buffer ESM is depicted in the following figure.
</p>

<p>
<a href="/_detail/doc/esm-table.jpg?id=doc%3Aesm_basic" class="media" title="doc:esm-table.jpg"><img src="/_media/doc/esm-table.jpg" class="media" alt="" /></a>
</p>

<p>
Every row of the table above correspond to exactly one transition in the ESM diagram in the first figure on this page. For example, the first row of the table above corresponds to the initial transition in the ESM diagram.

</p>

</div>
<!-- SECTION "Tabular Form" [5064-] -->