
---
title: Eclipse
layout: reference
---

<h1><a name="the_reactive_blocks_perspective" id="the_reactive_blocks_perspective">The Reactive Blocks Perspective</a></h1>
<div class="level1">

<p>

Eclipse organizes the views, actions and menus in the workspace by different perspectives.
After the installation, you can open the <strong>Reactive Blocks Perspective</strong>, which combines a number of useful views.
</p>

<p>
Here is how you open the perspective:
</p>

<p>

<a href="/_detail/doc/open-perspective4.jpg?id=doc%3Athe_arctis_perspective" class="media" title="doc:open-perspective4.jpg"><img src="/_media/doc/open-perspective4.jpg" class="media" title="Open the Reactive Blocks perspective" alt="Open the Reactive Blocks perspective" /></a>
</p>

<p>
There are several important views 
</p>
<ol>
<li class="level1"><div class="li"> The <strong>Building Block</strong> view, providing access to all building blocks, both the ones you create and those coming from libraries.</div>
</li>
<li class="level1"><div class="li"> The <strong>Java Package Explorer</strong> view which shows details of all Java code.</div>
</li>
<li class="level1"><div class="li"> The area for the <strong>Blocks Editor</strong>, the editor to create all sorts of building blocks.</div>
</li>
<li class="level1"><div class="li"> The <strong> Analysis </strong> view, showing the result of verifying a building block. This view is usually hidden. However you can open it quickly from the icon on the bottom right toolbar. </div>
</li>
</ol>

<p>

<a href="/_detail/doc/rb-perspective2.jpg?id=doc%3Athe_arctis_perspective" class="media" title="doc:rb-perspective2.jpg"><img src="/_media/doc/rb-perspective2.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "The Reactive Blocks Perspective" [1-914] -->
<h2><a name="tips_and_tricks" id="tips_and_tricks">Tips and Tricks</a></h2>
<div class="level2">
<ul>
<li class="level1"><div class="li"> If you close views or mess up our layout and want to restore it, you can select <em>Window | Reset Perspective</em> to come back.</div>
</li>
<li class="level1"><div class="li"> If you are an experienced Eclipse user you may have your own preferences about the layout of your workspace and do not need another perspective. Then just open the Blocks view.</div>
</li>
</ul>

</div>
<!-- SECTION "Tips and Tricks" [915-] -->

<h1><a name="the_blocks_editor" id="the_blocks_editor">The Blocks Editor</a></h1>
<div class="level1">

<p>

Reactive blocks are created and edited in the Blocks editor, which combines a couple of pages depending on the type of block.
</p>

<p>
<a href="/_detail/doc/rb-editor.jpg?id=doc%3Athe_arctis_editor" class="media" title="doc:rb-editor.jpg"><img src="/_media/doc/rb-editor.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "The Blocks Editor" [1-185] -->
<h2><a name="multiple_pages" id="multiple_pages">1. Multiple Pages</a></h2>
<div class="level2">

<p>
The editor displays models and code on different pages. Note that not all pages are present in all types of building blocks.
</p>
<ul>
<li class="level1"><div class="li"> The <strong>Behavior</strong> page shows a UML activity that describes the detailed behavior.</div>
</li>
<li class="level1"><div class="li"> The <strong>External</strong> page specifies the blocks interface via an <a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">External State Machine (ESM)</a>.</div>
</li>
<li class="level1"><div class="li"> The <strong>Documentation</strong> page is used to add descriptions to the block so others know how to use it.</div>
</li>
<li class="level1"><div class="li"> The <strong>Overview</strong> page summarizes information about the block and gives access to special operations. </div>
</li>
<li class="level1"><div class="li"> The <strong>System Overview</strong> page provides information about all the building blocks used in the diagram.</div>
</li>
</ul>

</div>
<!-- SECTION "1. Multiple Pages" [186-852] -->
<h2><a name="actions" id="actions">2. Actions</a></h2>
<div class="level2">

<p>
All actions that can be executed are chosen from the context menu. Individual pages show different menus, and the content of the menu also depends on the element selected.
</p>

</div>
<!-- SECTION "2. Actions" [853-1048] -->
<h2><a name="modeling_elements" id="modeling_elements">3. Modeling Elements</a></h2>
<div class="level2">

<p>
Modeling elements are also provided from the context menu. Depending on the <a href="/doc/building_blocks" class="wikilink1" title="doc:building_blocks">type of building blocks</a> being created, elements that are not allowed are not shown.
</p>

</div>
<!-- SECTION "3. Modeling Elements" [1049-1267] -->
<h2><a name="tips_and_tricks" id="tips_and_tricks">Tips and Tricks</a></h2>
<div class="level2">

</div>
<!-- SECTION "Tips and Tricks" [1268-1296] -->
<h3><a name="grid" id="grid">Grid</a></h3>
<div class="level3">

<p>

The editor has a grid, which is by default activated. You may hide it with the context menu. All nodes are aligned to the major grid (18 pixels). The bend-points of connections are aligned <em>in-between</em> the major grid. For that reason, fork and join nodes as well as actions should have an width or height that goes across an uneven number of grid spaces.
</p>

</div>
<!-- SECTION "Grid" [1297-1671] -->
<h3><a name="moving_and_re-sizing_elements" id="moving_and_re-sizing_elements">Moving and Re-sizing Elements</a></h3>
<div class="level3">

<p>

You may move all nodes using the arrow keys or by dragging them. Some elements, such as operations, forks, joins, set and get variable actions, receptions and guards, can be re-sized.
</p>

</div>
<!-- SECTION "Moving and Re-sizing Elements" [1672-1898] -->
<h3><a name="orientation_of_elements" id="orientation_of_elements">Orientation of Elements</a></h3>
<div class="level3">

<p>

The orientation of some nodes, like join, fork, input and output parameters, pins on operations and events, can be changed by pressing <em>"r"</em> (for rotate), as shown below. 
</p>

<p>
<a href="/_detail/doc/library.key.png?id=doc%3Athe_arctis_editor" class="media" title="doc:library.key.png"><img src="/_media/doc/library.key.png" class="media" alt="" /></a>
</p>

<p>
When an operation is rotated, its parameters are moving clockwise. When attached to the side, they are shown in their compact form without the parameter names and types.
</p>

<p>

To edit the pins on blocks, use <em>"r"</em> to switch the sides they are attached to, and the arrow keys to put them into place. (A current flaw makes that they may stick to a side and you have to press the arrow keys often to set their coordinates right.)
</p>

</div>
<!-- SECTION "Orientation of Elements" [1899-2558] -->
<h3><a name="connectors" id="connectors">Connectors</a></h3>
<div class="level3">

<p>
Once selected, the tools to create control or object flows stays active until you press <em>"r"</em> or select other element. Hence, you can create several connections at once.
</p>

</div>
<!-- SECTION "Connectors" [2559-2751] -->
<h3><a name="layout_tricks" id="layout_tricks">Layout Tricks</a></h3>
<div class="level3">

<p>

You can align the title bar of building blocks by a double click on it.
</p>

</div>
<!-- SECTION "Layout Tricks" [2752-2849] -->
<h2><a name="copy_and_paste" id="copy_and_paste">Copy and Paste</a></h2>
<div class="level2">

<p>

<strong>Copy</strong> and <strong>paste</strong> actions work on the following pages in the editor:
</p>
<ul>
<li class="level1"><div class="li"> On the behavior page you may copy groups of nodes and edges. If two connected edges are selected, the edge in between is copied, as well. Guards and selection statements are also copied, no matter if they are selected or not. This means you can focus on selecting which nodes you would like to copy, and the rest is taken care of automatically. Blocks are only copied completely, with all their pins.</div>
</li>
<li class="level1"><div class="li"> On the ESM page, transitions may be copied and pasted. If a transition refers to a parameter node that is not present in the building block it is pasted in, this parameter node is created.</div>
</li>
<li class="level1"><div class="li"> On the Events page, entire events with their parameters can be copied. </div>
</li>
</ul>

<p>
Some hints:
</p>
<ul>
<li class="level1"><div class="li"> The clipboard keeps ESM transitions, events or activity elements separately. Therefore, you may copy some ESM transitions, then some activity nodes, then paste ESM transitions and afterwards paste the activity nodes or vice versa.</div>
</li>
<li class="level1"><div class="li"> At the moment, copy and paste are not mapped to the standard key bindings (Ctrl-C, Ctrl-V).</div>
</li>
</ul>

<p>

<strong>Duplicate</strong> is an dedicated action when you would just like to copy and paste some elements within the same building block, for instance when you want to create some similar ESM transitions, events or sub graphs. Duplicate does not interfere with what is stored in the clipboard.
</p>

</div>
<!-- SECTION "Copy and Paste" [2850-] -->