---
title: Advanced Issues
layout: reference
---


<h1><a name="advanced_issues" id="external_interfaces_3advanced_issues">Advanced Issues</a></h1>
<div class="level1">

<p>

The basic concept of ESMs is described <a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">here</a>. Make sure you have read about  <a href="/doc/semantics" class="wikilink1" title="doc:semantics">the semantics of activities</a> first. 
</p>

</div>
<!-- SECTION "External Interfaces 3: Advanced Issues" [1-203] -->
<h2><a name="implicit_termination" id="implicit_termination">Implicit Termination</a></h2>
<div class="level2">

<p>

You may find an ESM transition labelled with <strong>/</strong> and points to a final state. This is called <strong>implicit termination</strong>.
</p>

<p>
As an example, see the following figure.
</p>

<p>

<a href="/_detail/doc/implicit-termination.jpg?id=doc%3Aesm_advanced" class="media" title="doc:implicit-termination.jpg"><img src="/_media/doc/implicit-termination.jpg" class="media" alt="" /></a>
</p>

<p>

This is the ESM of block Timer Periodic. The rightmost hand-side is an example of implicit termination.
It allows the surrounding (enclosing) block to terminate while the Timer Periodic block is in state active, without invoking any parameter or pin of Timer Periodic.
</p>

<p>
Implicit termination is typically used for blocks that do not need to release resources and in <a href="/doc/building_blocks" class="wikilink1" title="doc:building_blocks">shallow blocks</a>.
</p>

</div>
<!-- SECTION "Implicit Termination" [204-846] -->
<h2><a name="multiple_pin_labels" id="multiple_pin_labels">Multiple Pin Labels</a></h2>
<div class="level2">

<p>

From the basic concept of ESMs, you have learned that transition labels can have two pins. In fact, they can include <strong>any number of pins</strong>.
</p>

<p>
The ESM of Timer Periodic block, for instance, has a transition with three pins.
</p>

<p>
<a href="/_detail/doc/multiple-pins.jpg?id=doc%3Aesm_advanced" class="media" title="doc:multiple-pins.jpg"><img src="/_media/doc/multiple-pins.jpg" class="media" alt="" /></a>
</p>

<p>
Transition <strong>/tick; stop; stopped</strong> involves three pins, i.e., output pin tick, input pin stop and output pin stopped.
Note that the sequence of those pins is important.
For this example, the block will emit event tick and subsequently (but without delay) receive input event stop and then emit an output via pin stopped.
</p>

<p>
The semicolons (<strong>;</strong>) are used to help reading the label easier.
It separates <strong>different groups of pins</strong>.
<strong>A group either consists only of input or output pins</strong>.
Therefore, for the transition above we have three groups, i.e., output-pin group, input-pin group and another output-pin group.
Each group consists of a single pin, “tick, “stop”, and “stopped” respectively.
</p>

<p>

A group can contain more than one pin. Plus sign (<strong>+</strong>) is used to <strong>separate pins within a group</strong>.
</p>

<p>

As mentioned previously, the transition <em>”/tick; stop; stopped”</em> allows block Timer Periodic to be stopped right after a “tick”.
This means that the use of the block depicted in the following figure is allowed by the ESM.
</p>

<p>
<a href="/_detail/doc/timer-periodic-esm-ok.jpg?id=doc%3Aesm_advanced" class="media" title="doc:timer-periodic-esm-ok.jpg"><img src="/_media/doc/timer-periodic-esm-ok.jpg" class="media" alt="" /></a>
</p>

<p>

Let us remove the transition mentioned above, as also illustrated by the ESM of block “Timer Periodic Stop Delayed” in the following figure.
</p>

<p>
<a href="/_detail/doc/timer-periodic-stop-delayed.png?id=doc%3Aesm_advanced" class="media" title="doc:timer-periodic-stop-delayed.png"><img src="/_media/doc/timer-periodic-stop-delayed.png" class="media" alt="" /></a>
</p>

<p>

For the new block, the direct flow from pin <em>tick</em> to pin <em>stop</em> is not allowed.
The ESM diagram of block Timer Periodic Stop Delayed shows that stopping the block from pin “tick” needs another transition invoking pin “stop” (and “stopped”) which <strong>cannot be combined</strong> with the transition involving pin tick.
Therefore, <strong>two separate <a href="/doc/semantics" class="wikilink1" title="doc:semantics">activity steps</a></strong> are needed. (See also this <a href="/issues/ae1#example_1illegal_synchronous_step" class="wikilink1" title="issues:ae1">example</a>)
</p>

<p>

To cut the single activity step from pin “tick” to pin “stop”, a timer can be used. If no delay is necessary, then you can set the duration of the <a href="/doc/timers#timers_with_0_ms_duration" class="wikilink1" title="doc:timers">timer to 0 ms</a> as depicted in the bottom half of the following figure.
</p>

<p>
<a href="/_detail/doc/timer-periodic-stop-delayed-example.jpg?id=doc%3Aesm_advanced" class="media" title="doc:timer-periodic-stop-delayed-example.jpg"><img src="/_media/doc/timer-periodic-stop-delayed-example.jpg" class="media" alt="" /></a>
</p>

<p>
Note that you cannot use an operation, set and get actions, decision and merge nodes instead of the timer. These nodes are <strong><a href="/doc/semantics#stable_positions" class="wikilink1" title="doc:semantics">not stable positions</a></strong>.
</p>

</div>
<!-- SECTION "Multiple Pin Labels" [847-] -->