---
title: Animation
layout: reference
---

<h1><a name="animation" id="animation">Animation</a></h1>
<div class="level1">

<p>

The Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> includes an animation feature that can show how the token flows through activity nodes and edges. You can control the animation by executing one <a href="/doc/semantics" class="wikilink1" title="doc:semantics">activity step</a> at a time. This feature is very useful to help you understand the behavior of a building block and also to find potential problems.
</p>

</div>
<!-- SECTION "Animation" [1-359] -->
<h2><a name="enter_animation_mode" id="enter_animation_mode">Enter Animation Mode</a></h2>
<div class="level2">

<p>
You can start the animation feature by choosing action <em>Animate</em> from the context menu or by clicking the green triangle icon on the top right of the Behavior page (see the following figure).
</p>

<p>
All <a href="/doc/building_blocks" class="wikilink1" title="doc:building_blocks">types of building block</a> can be animated.
</p>

<p>

<a href="/_detail/doc/start-animation3.jpg?id=doc%3Aanimation" class="media" title="doc:start-animation3.jpg"><img src="/_media/doc/start-animation3.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Enter Animation Mode" [360-692] -->
<h2><a name="controlling_animation" id="controlling_animation">Controlling Animation</a></h2>
<div class="level2">

<p>
Below is a figure showing how animating a block looks like.
</p>

<p>
<a href="/_detail/doc/animation-3.jpg?id=doc%3Aanimation" class="media" title="doc:animation-3.jpg"><img src="/_media/doc/animation-3.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> The current state of the building block is shown below the title (e.g., <em>active</em> in the figure above). Note that if the block is of type system, its state is not shown.</div>
</li>
<li class="level1"><div class="li"> The current state of each inner block is also shown similarly (e.g., in the figure above the block <strong>Send Email</strong> is currently in state <em>sending</em>)</div>
</li>
<li class="level1"><div class="li"> The activity step that will be taken is shown by highlighting the nodes and edges with yellow background</div>
</li>
</ul>

<p>
A window titled Animation <strong>(1)</strong> is opened displaying keys that can be used to control animation.
</p>
<ul>
<li class="level1"><div class="li"> <em>Down</em> arrow is used to execute the activity step that is highlighted.</div>
</li>
<li class="level1"><div class="li"> <em>Up</em> arrow is used to undo a step.</div>
</li>
<li class="level1"><div class="li"> <em>Left</em> (←-) and <em>right</em> (–&gt;) arrows are used to switch between alternative executable steps <strong>(2)</strong></div>
</li>
<li class="level1"><div class="li"> Key <em>i</em> is used to restart animation.</div>
</li>
</ul>

<p>

The Animation window also shows issues with the activity step or state, if any.
</p>

</div>
<!-- SECTION "Controlling Animation" [693-1707] -->
<h2><a name="more_details" id="more_details">More Details</a></h2>
<div class="level2">

<p>
We can also find out which ESM transition is taken by every block in a chosen activity step. For example, in the figure above, let us find out the ESM transition taken by the inner block <em>Send Email</em> in the highlighted activity step.
</p>

<p>
Just open the ESM by selecting <em>Show ESM</em> from the context menu of block <em>Send Email</em> (see the figure below). You will get window <strong>(1)</strong> displaying the ESM with transition <em>/ok</em> highlighted.
</p>

<p>
<a href="/_detail/doc/animation-3a.jpg?id=doc%3Aanimation" class="media" title="doc:animation-3a.jpg"><img src="/_media/doc/animation-3a.jpg" class="media" alt="" /></a>
</p>

<p>
Note that in any activity step, each inner block can participate by maximal one ESM transition.
</p>

</div>
<!-- SECTION "More Details" [1708-2293] -->
<h2><a name="exit_animation_mode" id="exit_animation_mode">Exit Animation Mode</a></h2>
<div class="level2">

<p>
To exit the animation, close the window called “Animation”.
</p>

</div>
<!-- SECTION "Exit Animation Mode" [2294-2387] -->
<h3><a name="tips" id="tips">Tips</a></h3>
<div class="level3">
<ul>
<li class="level1"><div class="li"> The Animation and ESMs windows can be moved around</div>
</li>
<li class="level1"><div class="li"> You may need to solve some errors (usually related to construction) before you can animate a building block.</div>
</li>
</ul>

</div>
<!-- SECTION "Tips" [2388-] -->