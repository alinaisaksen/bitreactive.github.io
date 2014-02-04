---
title: Editing Data Flows
layout: reference
---


<h1><a name="activity_edges" id="activity_edges">Activity Edges</a></h1>
<div class="level1">

<p>

Activity Edges are elements of <a href="/doc/activity_diagram_overview" class="wikilink1" title="doc:activity_diagram_overview">Activity Diagrams</a> and used to connect <a href="/doc/activity_diagram_nodes" class="wikilink1" title="doc:activity_diagram_nodes">Activity Nodes</a> and <a href="/doc/building_blocks" class="wikilink1" title="doc:building_blocks">Reactive Blocks</a>.
</p>

</div>
<!-- SECTION "Activity Edges" [1-226] -->
<h3><a name="control_and_object_flows" id="control_and_object_flows">Control and Object Flows</a></h3>
<div class="level3">

<p>

Activity nodes are connected by edges, which exist in two types:
</p>
<ul>
<li class="level1"><div class="li"> <strong>Object flows</strong> are shown as thick blue lines. These flows can transport data.</div>
</li>
<li class="level1"><div class="li"> <strong>Control flows</strong> are shown as thin black lines. Control flows do not carry any data.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/flows3.jpg?id=doc%3Aactivity_diagram_edges" class="media" title="doc:flows3.jpg"><img src="/_media/doc/flows3.jpg" class="media" alt="" /></a>
</p>

<p>

Notice that object and control flows are not necessarily implemented as signals or objects that are passed between activity elements, this is just an illustration of the semantics. Object flows can be implemented for instance by variables. 
</p>

</div>
<!-- SECTION "Control and Object Flows" [227-768] -->
<h3><a name="control_or_object_flows" id="control_or_object_flows">Control or Object Flows?</a></h3>
<div class="level3">

<p>
Control flows are just a notification about an event, while <strong>object flows also carry data objects</strong>. To determine if you need an object flow or a control flow, focus on the nodes that they target: If nodes require data (such as input pins of operations), use an object flow.
</p>

<p>

Some building blocks or operations may provide objects that you are not always interested in. For example, a building block provides an exception object, but for you it only counts that an exception happened. Then you may simply ignore that the pin is types and continue with an control flow.
</p>

<p>
From a technical point of view, you could always use object nodes. However, we recommend to use control flows wherever possible to make visible that no data is transferred.
</p>

</div>
<!-- SECTION "Control or Object Flows?" [769-1550] -->
<h3><a name="creating_activity_edges" id="creating_activity_edges">Creating Activity Edges</a></h3>
<div class="level3">

<p>

To create an edge, select Add… / Edge from the context menu. This tool stays selected, so you can add more than one edge. To change into normal selection mode, choose Select, or press Esc.
</p>

<p>
<a href="/_detail/doc/create-edge.png?id=doc%3Aactivity_diagram_edges" class="media" title="doc:create-edge.png"><img src="/_media/doc/create-edge.png" class="media" alt="" /></a>
</p>

<p>
The editor will try to guess if the edge should be a control flow or an object flow. Object flows are chosen whenever the downstream nodes require data or the upstream nodes provide data. This strategy is right in most cases. If, however, the editor choses an control flow but you want an object flow or the other way around, you can simply right-click the newly created edge and select <strong>Switch to Object Flow</strong> (or vice-versa).
</p>

<p>
<a href="/_detail/doc/switch-flow-types.png?id=doc%3Aactivity_diagram_edges" class="media" title="doc:switch-flow-types.png"><img src="/_media/doc/switch-flow-types.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Creating Activity Edges" [1551-2268] -->
<h3><a name="working_with_bend_points" id="working_with_bend_points">Working with Bend Points</a></h3>
<div class="level3">

<p>

You may want to bend points in order to make your diagram more readable. In order to do this, select the edge with your pointer, then drag the bend-point on the middle.
</p>

<p>
<a href="/_detail/doc/connector.jpg?id=doc%3Aactivity_diagram_edges" class="media" title="doc:connector.jpg"><img src="/_media/doc/connector.jpg" class="media" alt="" /></a>
</p>

<p>
To make a bent line straight do the exact opposite, i.e. drag the middle bend point back to its original position.
</p>

<p>
<a href="/_detail/doc/connector2.jpg?id=doc%3Aactivity_diagram_edges" class="media" title="doc:connector2.jpg"><img src="/_media/doc/connector2.jpg" class="media" alt="" /></a>
</p>
<div class="box left" style="width: 100%; background-color: rgb(237,241,244); border-color: rgb(70,105,139);">
  <b class='xtop'><b class='xb1' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);"></b><b class='xb2' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);"></b><b class='xb3' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);"></b><b class='xb4' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);"></b></b>
  <div class='xbox' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);">
<p class='box_title'style="background-color: rgb(237,241,244);"><strong>Tip: Converting the flow type</strong></p>
<div class='box_content'style="background-color: rgb(237,241,244); border-color: rgb(70,105,139)">
You may convert an object flow into a control flow and vice versa with a dedicated action in the context menu of a flow. 
<p>
This action also preserves the layout with all bend points. 

</p>
</div>
  </div>
  <b class='xbottom'><b class='xb4' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);"></b><b class='xb3' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);"></b><b class='xb2' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);"></b><b class='xb1' style="background-color: rgb(237,241,244); border-color: rgb(70,105,139);"></b></b>
</div>

</div>
<!-- SECTION "Working with Bend Points" [2269-2919] -->
<h3><a name="flows_and_pins" id="flows_and_pins">Flows and Pins</a></h3>
<div class="level3">

<p>

Flows are used to connect Reactive Blocks with other Reactive Blocks or Activity Nodes. The pins of a block provide the interface for ingoing and outgoing data of a block. Even so there are different types of pins (starting pin, terminating pin, streaming input pin, streaming output pin) and different types of flows (object and control flows), there is no restriction in connecting flows to pins. <strong>Both flow types may be connected to all pin types.</strong>
</p>

</div>
<!-- SECTION "Flows and Pins" [2920-3403] -->
<h3><a name="decisions_and_guards" id="decisions_and_guards">Decisions and Guards</a></h3>
<div class="level3">

<p>
Add guards to activity flows by using the context menu of the flow. During the execution, a decision must <strong>not block</strong>, that means, at least one branch must have a guard that is true. This can be achieved by always having one &#039;else&#039;-branch. If several guards are true, an arbitrary one is chosen.
</p>

<p>

<a href="/_detail/doc/guard.jpg?id=doc%3Aactivity_diagram_edges" class="media" title="doc:guard.jpg"><img src="/_media/doc/guard.jpg" class="media" alt="" /></a>
</p>

</div>

<h4><a name="boolean_guards" id="boolean_guards">Boolean Guards</a></h4>
<div class="level4">

<p>

To make a decision dependent on a boolean value provided by an operation, simply use a pair of outgoing branches from a decision node, and add the guards <code>true</code> and <code>false</code>. The edges entering and leaving the decision nodes need to be object flows, since they transport the boolean value to the guards.
</p>

<p>
<a href="/_detail/doc/guard-boolean.jpg?id=doc%3Aactivity_diagram_edges" class="media" title="doc:guard-boolean.jpg"><img src="/_media/doc/guard-boolean.jpg" class="media" alt="" /></a>
</p>

</div>

<h4><a name="constant_strings_and_integers" id="constant_strings_and_integers">Constant Strings and Integers</a></h4>
<div class="level4">

<p>

To decide between more than two branches, you can use <strong>literal values</strong>. In the example, the operation produces a string value, which is then compared with the literal string values specified by each outgoing branch. To make sure that the decision is non-blocking, you must add an else branch in any case. Literal integers can be specified as well.
</p>

<p>
<a href="/_detail/doc/guard-string-int2.jpg?id=doc%3Aactivity_diagram_edges" class="media" title="doc:guard-string-int2.jpg"><img src="/_media/doc/guard-string-int2.jpg" class="media" alt="" /></a>
</p>

</div>

<h4><a name="passing_data_around_guards" id="passing_data_around_guards">Passing Data Around Guards</a></h4>
<div class="level4">

<p>

In some cases, the downstream branches need some data that is not the same as the data we want to work with in the guards. Below, for instance, shows part of a specification that lets users subscribe to a serivce via SMS. From the incoming SMS we extract the keyword and compare it with the literal string guards on each branch. This means that the operation <code>extractType</code> provides a String. However, downstream we would like to use the complete SMS again. Therefore, we use an extra variable <code>currentIncSMS</code> as a <strong>temporal buffer</strong> to store the SMS, and use set and get operations.
</p>

<p>

<a href="/_detail/doc/guard-data2.jpg?id=doc%3Aactivity_diagram_edges" class="media" title="doc:guard-data2.jpg"><img src="/_media/doc/guard-data2.jpg" class="media" alt="" /></a>
</p>

</div>

<h4><a name="boolean_method_guards" id="boolean_method_guards">Boolean Method Guards</a></h4>
<div class="level4">

<p>

Boolean methods can also be used as guards. These can be used instead of boolean guards and are useful to make your specifications <strong>more compact and easier to understand</strong>. Moreover, the object flows that are connected to the decision node can be use to  other data. See the following figure.
</p>

<p>
<a href="/_detail/doc/guard-boolean-method2.jpg?id=doc%3Aactivity_diagram_edges" class="media" title="doc:guard-boolean-method2.jpg"><img src="/_media/doc/guard-boolean-method2.jpg" class="media" alt="" /></a>
</p>

<p>
The left and right models have the same behavior. If operation <code>isStudent()</code> returns true, operation <code>studentOp(User u)</code> is executed; otherwise, operation <code>elseOp(User u)</code> is called.
On the left part, operation <code>isStudent()</code> is used as a guard. Note that, here the flows in and out the decision node contain an object of type<code>User</code>. In contrast, the incoming and outgoing flows of the decision node on the right part have a boolean object.
</p>

<p>
This type of guards can <strong>only</strong> be used with boolean methods with <strong>no parameter</strong>.
</p>

</div>
<!-- SECTION "Decisions and Guards" [3404-] -->