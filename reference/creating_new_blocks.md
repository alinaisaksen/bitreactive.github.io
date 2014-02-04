---
title: Activity Nodes
layout: reference
---

<h1><a name="create_a_new_project" id="create_a_new_project">Create a New Project</a></h1>
<div class="level1">

<p>

Start by creating a new project. 

</p>
<ul>
<li class="level1"><div class="li"> Select File / New / Other…</div>
</li>
<li class="level1"><div class="li"> Select <strong>Reactive Blocks Project</strong></div>
</li>
</ul>

<p>

<a href="/_detail/doc/new-project-wizard.png?id=doc%3Acreating_new_building_blocks" class="media" title="doc:new-project-wizard.png"><img src="/_media/doc/new-project-wizard.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Create a New Project" [1-179] -->
<h1><a name="create_a_new_block" id="create_a_new_block">Create a New Block</a></h1>
<div class="level1">

<p>

Reactive Blocks can be created in two ways:

</p>
<ul>
<li class="level1"><div class="li"> <strong>With the New Reactive Block Wizard.</strong> This wizard creates a new building block from a template. These templates are usually very simple, such as an empty local building block or a simple Hello World example. See below for an introduction how this wizard is used.</div>
</li>
<li class="level1"><div class="li"> <strong>As a Duplicate of an Existing Block.</strong> Existing reactive blocks can be duplicated, using the corresponding method from the context menu in the Reactive Block view. Note that all details of a reactivve block are duplicated, but not the Java code. </div>
</li>
</ul>

</div>
<!-- SECTION "Create a New Block" [180-782] -->
<h2><a name="new_building_block_wizard" id="new_building_block_wizard">New Building Block Wizard</a></h2>
<div class="level2">

<p>
There are several ways to open the wizard:
</p>
<ul>
<li class="level1"><div class="li"> Use shortcut “<strong>New…</strong>” on the upper right of the Building Block view.</div>
</li>
<li class="level1"><div class="li"> Choose action <em>“New Block…”</em> from the context menu of a project in the Building Block view.</div>
</li>
<li class="level1"><div class="li"> Choose <em>File –&gt; New –&gt; Other</em> and thereafter choose <em>“Building Block”</em> from the opened window (see the figure below)</div>
</li>
</ul>

<p>
<a href="/_detail/doc/new-bb2.jpg?id=doc%3Acreating_new_building_blocks" class="media" title="doc:new-bb2.jpg"><img src="/_media/doc/new-bb2.jpg" class="media" alt="" /></a>
</p>

<p>

The wizard is shown in the figure below.
</p>

<p>
<a href="/_detail/doc/new-bb-wizard3.jpg?id=doc%3Acreating_new_building_blocks" class="media" title="doc:new-bb-wizard3.jpg"><img src="/_media/doc/new-bb-wizard3.jpg" class="media" alt="" /></a>

</p>
<ol>
<li class="level1"><div class="li"> You have to fill in a new <strong>name</strong> for the block using letters, numbers and spaces.</div>
</li>
<li class="level1"><div class="li"> Choose one from available <strong>templates</strong>. See the page about <a href="/doc/building_blocks" class="wikilink1" title="doc:building_blocks">types of building block</a> to help you choosing a correct template.</div>
</li>
<li class="level1"><div class="li"> Which <strong>project</strong> should the block be placed in. All building blocks within one project must have unique names.</div>
</li>
</ol>

<p>

A building block is shown in the <a href="/doc/the_arctis_editor" class="wikilink1" title="doc:the_arctis_editor">Blocks Editor</a> by finishing the wizard above.
Thereafter, depending on the <a href="/doc/building_blocks" class="wikilink1" title="doc:building_blocks">type</a> of building block you created you can do several actions.
</p>

</div>
<!-- SECTION "New Building Block Wizard" [783-] -->




<h1><a name="creating_system_blocks" id="creating_system_blocks">Creating System Blocks</a></h1>
<div class="level1">

<p>

Check this <a href="/doc/creating_new_building_blocks" class="wikilink1" title="doc:creating_new_building_blocks">page</a> in order to create a new building block. Remember to choose <strong>System Block</strong> template in the new building block wizard.
</p>

<p>
A system block has internal behavior (activity diagram) and optionally Java code. Only from this type of block the <acronym title="Software Development Kit">SDK</acronym> will generate an executable code.
</p>

<p>
The following figure shows an example of a system block shown in the Blocks Editor.
</p>

<p>
<a href="/_detail/doc/create-system-block2.jpg?id=doc%3Acreating_system_blocks" class="media" title="doc:create-system-block2.jpg"><img src="/_media/doc/create-system-block2.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Creating System Blocks" [1-488] -->
<h2><a name="activity_diagram_and_java_code" id="activity_diagram_and_java_code">Activity Diagram and Java Code</a></h2>
<div class="level2">

<p>

The activity diagram is specified on the <em>Behavior</em> page as exemplified by the figure above. Here, you can:

</p>
<ul>
<li class="level1"><div class="li"> <a href="/doc/using_building_blocks#instantiating_blocks" class="wikilink1" title="doc:using_building_blocks">instantiate</a> local blocks taken from <a href="/doc/discovery" class="wikilink1" title="doc:discovery">libraries or projects</a>.</div>
</li>
<li class="level1"><div class="li"> add/modify <a href="/doc/activity_nodes" class="wikilink1" title="doc:activity_nodes">activity nodes</a></div>
</li>
<li class="level1"><div class="li"> connect activity nodes and inner blocks with <a href="/doc/control_and_object_flows" class="wikilink1" title="doc:control_and_object_flows">flows</a></div>
</li>
</ul>

<p>

If your block has <a href="/doc/activity_nodes#operations" class="wikilink1" title="doc:activity_nodes">operations</a>, you need to specify the <a href="/doc/java_operations" class="wikilink1" title="doc:java_operations">Java methods</a> they refer to in the <em>_.java</em> page.
In the example depicted in the above figure, operation <em>makeFeed</em>, <em>initRecordData</em>, and <em>showMsg</em> are defined on page <em>Component.java</em>.
</p>

<p>
If your block contains <a href="/doc/activity_nodes#events" class="wikilink1" title="doc:activity_nodes">events</a>, add/modify them on the <em>Events</em> page.
</p>

<p>
If you need to use external <a href="/doc/java_libraries" class="wikilink1" title="doc:java_libraries">Java libraries or other resources</a>, list them on the <em>Overview</em> page.
</p>

</div>
<!-- SECTION "Activity Diagram and Java Code" [489-1452] -->
<h2><a name="initial_nodes_and_activity_final_nodes" id="initial_nodes_and_activity_final_nodes">Initial Nodes and Activity Final Nodes</a></h2>
<div class="level2">

<p>
A system building block does not have <a href="/doc/creating_local_blocks#parameter_nodes" class="wikilink1" title="doc:creating_local_blocks">parameter nodes</a> as it is not intended to be reused. However, we can use <a href="/doc/activity_nodes#initial_nodes" class="wikilink1" title="doc:activity_nodes">initial nodes</a> to start the system and <a href="/doc/activity_nodes#activity_final_nodes" class="wikilink1" title="doc:activity_nodes">activity final nodes</a> to terminate it.
</p>

<p>
In the figure above, there is one initial node and no terminating node. Termination is implied, namely after calling operation <em>showMsg</em>.
</p>

</div>
<!-- SECTION "Initial Nodes and Activity Final Nodes" [1453-1958] -->
<h2><a name="block_s_documentation" id="block_s_documentation">Block&#039;s Documentation</a></h2>
<div class="level2">

<p>

You can add <a href="/doc/block_descriptions" class="wikilink1" title="doc:block_descriptions">management information</a> about this block on page <em>Overview</em> and <em>Documentation</em>.
</p>

<p>
On the <em>System Overview</em> page, you can see some information about the block and its inner blocks.
</p>

</div>
<!-- SECTION "Block's Documentation" [1959-2219] -->
<h2><a name="implementing_a_system" id="implementing_a_system">Implementing a System</a></h2>
<div class="level2">

<p>
Before generating executable code, it is a good idea to check the activity diagram of the system block for errors or issues and whether it behaves as intended. For these, you can use the <a href="/doc/analysis" class="wikilink1" title="doc:analysis">analyzer</a> and <a href="/doc/animation" class="wikilink1" title="doc:animation">animator</a> tools respectively.
</p>

<p>
When you are sure that the behavior is correct, then you can implement the block as described <a href="/doc/implementing_a_system" class="wikilink1" title="doc:implementing_a_system">here</a>.

</p>

</div>
<!-- SECTION "Implementing a System" [2220-] -->




<h1><a name="creating_local_blocks" id="creating_local_blocks">Creating Local Blocks</a></h1>
<div class="level1">

<p>

Check this <a href="/doc/creating_new_building_blocks" class="wikilink1" title="doc:creating_new_building_blocks">page</a> in order to create a new building block. Remember to choose <strong>Local Block</strong> template in the new building block wizard.
</p>

<p>
A local block has internal behavior (activity diagram), external behavior (ESM), and optionally Java code.
This type of block is intended to be (re)used or instantiated within other local blocks or system blocks.
</p>

<p>
The following figure shows an example of a local block shown in the Blocks Editor.
</p>

<p>
<a href="/_detail/doc/create-local-block3.jpg?id=doc%3Acreating_local_blocks" class="media" title="doc:create-local-block3.jpg"><img src="/_media/doc/create-local-block3.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Creating Local Blocks" [1-543] -->
<h2><a name="activity_diagram_and_java_code" id="activity_diagram_and_java_code">Activity Diagram and Java Code</a></h2>
<div class="level2">

<p>

Activity diagram is specified on the <em>Behavior</em> page as exemplified in the figure above. Here, you can:

</p>
<ul>
<li class="level1"><div class="li"> <a href="/doc/using_building_blocks#instantiating_blocks" class="wikilink1" title="doc:using_building_blocks">instantiate</a> other (inner) blocks taken from <a href="/doc/discovery" class="wikilink1" title="doc:discovery">libraries or projects</a>.</div>
</li>
<li class="level1"><div class="li"> add/modify <a href="/doc/activity_nodes" class="wikilink1" title="doc:activity_nodes">activity nodes</a></div>
</li>
<li class="level1"><div class="li"> connect activity nodes and inner blocks with <a href="/doc/control_and_object_flows" class="wikilink1" title="doc:control_and_object_flows">flows</a></div>
</li>
</ul>

<p>

If your block has <a href="/doc/activity_nodes#operations" class="wikilink1" title="doc:activity_nodes">operations</a>, you need to specify the <a href="/doc/java_operations" class="wikilink1" title="doc:java_operations">Java methods</a> they refer to in the <em>_.java</em> page. In the example above, operation <em>timeout</em> is defined on page <em>SendEmail.java</em>.
</p>

<p>
If your block contains <a href="/doc/activity_nodes#events" class="wikilink1" title="doc:activity_nodes">events</a>, add/modify them on the <em>Events</em> page.
</p>

<p>
If you need to use external <a href="/doc/java_libraries" class="wikilink1" title="doc:java_libraries">Java libraries or other resources</a>, list them on the <em>Overview</em> page.
</p>

<p>
If you need <a href="/doc/instance_parameters_for_building_blocks#adding_instance_parameters_to_a_building_block" class="wikilink1" title="doc:instance_parameters_for_building_blocks">instance parameters</a> in your block, add them also on the <em>Overview</em> page.
</p>

</div>
<!-- SECTION "Activity Diagram and Java Code" [544-1633] -->
<h2><a name="parameter_nodes" id="parameter_nodes">Parameter Nodes</a></h2>
<div class="level2">

<p>
Since this type of block is meant to be used in other enclosing blocks, initial and activity final nodes should not be used.
However, a local block must have parameter nodes on its edge.
When a local block is instantiated these nodes are referred as <a href="/doc/using_building_blocks#pins" class="wikilink1" title="doc:using_building_blocks">pins</a> and used to connect the instance with other modeling elements.
There are several types of parameter nodes as depicted in the figure below.
</p>

<p>
<a href="/_detail/doc/parameter-nodes4.jpg?id=doc%3Acreating_local_blocks" class="media" title="doc:parameter-nodes4.jpg"><img src="/_media/doc/parameter-nodes4.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Starting and terminating parameters are used to start and terminate a local block respectively. These nodes have white background. They are used to control the life cycle of a block instance. Formally a local block does not need to have a starting or terminating pin. However, for most blocks it makes sense to provide  starting and terminating pins to make this block easier to use.</div>
</li>
<li class="level1"><div class="li"> Streaming input and output are used when a block is active. These nodes have black background.</div>
</li>
<li class="level1"><div class="li"> If a block terminates with different alternative result, then the nodes are shown in double frame. (It is also possible to start a block in several ways, but it is very seldom.)</div>
</li>
</ul>

<p>
All types of pin can be used with all types of flows. So no matter if a pin is a starting or terminating or streaming pin, it can be connected using a control or a object flow.
</p>

<p>
Note that data can flow in and out of local blocks through parameter nodes. In this case the parameter nodes have data types like the parameter node <em>in</em> above (It can carry an object of type <code>String</code>). You can add type by choosing <em>“Data type”</em> from the context menu of a parameter node.
</p>

</div>
<!-- SECTION "Parameter Nodes" [1634-3269] -->
<h2><a name="external_interface" id="external_interface">External Interface</a></h2>
<div class="level2">

<p>

A local block must have a corresponding external interface or ESM. This is important, so that the block can be reused without looking and understanding the internal behavior. <a href="/doc/esm_creation" class="wikilink1" title="doc:esm_creation">Creating/Editing ESM</a> is done on the <em>External</em> page.
</p>

</div>
<!-- SECTION "External Interface" [3270-3554] -->
<h2><a name="block_s_documentation" id="block_s_documentation">Block&#039;s Documentation</a></h2>
<div class="level2">

<p>

In order to help other developers reusing your block, you can add <a href="/doc/block_descriptions" class="wikilink1" title="doc:block_descriptions">management information</a> like the status of your block, its purpose, its parameter nodes, etc. on the <em>Overview</em> and <em>Documentation</em> pages.
</p>

<p>
On the <em>System Overview</em> page, you can see some information about the block and its inner blocks.

</p>

</div>
<!-- SECTION "Block's Documentation" [3555-] -->




<h1><a name="creating_shallow_blocks" id="creating_shallow_blocks">Creating Shallow Blocks</a></h1>
<div class="level1">

<p>

Check this <a href="/doc/creating_new_building_blocks" class="wikilink1" title="doc:creating_new_building_blocks">page</a> in order to create a new building block. Remember to choose <strong>Shallow Block</strong> template in the new building block wizard.
</p>

<p>
A shallow block only has parameter nodes and external behavior (ESM).
It does not contain any Java code.
Like local block, this type of block is intended to be reused in local or system blocks.
Its main purpose is to coordinate flows in an activity diagram in a more powerful way than what the activity nodes like joins allow.
</p>

<p>

An example of a shallow block&#039;s parameter nodes and its ESM is depicted in the following figure.
</p>

<p>
<a href="/_detail/doc/block-shallow-example2.png?id=doc%3Acreating_shallow_blocks" class="media" title="doc:block-shallow-example2.png"><img src="/_media/doc/block-shallow-example2.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Creating Shallow Blocks" [1-680] -->
<h2><a name="adding_parameters" id="adding_parameters">Adding Parameters</a></h2>
<div class="level2">

<p>
Adding a parameter node is done from the context menu on page <em>Parameter</em>. You will get a window as depicted in the following figure.
</p>

<p>
<a href="/_detail/doc/add-param-shallow-block2.jpg?id=doc%3Acreating_shallow_blocks" class="media" title="doc:add-param-shallow-block2.jpg"><img src="/_media/doc/add-param-shallow-block2.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> <strong>1</strong> Fill in the name of the parameter</div>
</li>
<li class="level1"><div class="li"> <strong>2</strong> Choose the type of the parameter</div>
</li>
</ul>

<p>

Parameter nodes of a shallow block are similar to the ones of a <a href="/doc/creating_local_blocks#parameter_nodes" class="wikilink1" title="doc:creating_local_blocks">local block</a>. The only difference is that data types cannot be attached to parameter nodes on a shallow block. However, this <strong>does not mean that data or objects cannot flow through shallow blocks</strong>. 
For an instance of block <em>Switcher</em> depicted above, if you connect its input pin <em>in</em> with a data flow, the data will be passed through its output pins, either <em>out1</em> or <em>out2</em>, and thus those output pins have to be connected with data flows.
The <acronym title="Software Development Kit">SDK</acronym> gives out an error message when if the outgoing edges are control flows.
</p>

</div>
<!-- SECTION "Adding Parameters" [681-1619] -->
<h2><a name="external_interface" id="external_interface">External Interface</a></h2>
<div class="level2">

<p>

The behavior of a shallow block is specified solely by its external interface or ESM. Therefore, you have to attach the block with an ESM. <a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">Creating/Editing ESM</a> is done on the External page.
</p>

</div>
<!-- SECTION "External Interface" [1620-1861] -->
<h2><a name="block_s_documentation" id="block_s_documentation">Block&#039;s Documentation</a></h2>
<div class="level2">

<p>

In order to help other developers reusing your block, you can add <a href="/doc/building_blocks#management_info_for_building_blocks" class="wikilink1" title="doc:building_blocks">management information</a> like the status of your block, its purpose, its parameter nodes, etc. on the <em>Overview</em> and <em>Documentation</em> pages.
</p>

</div>
<!-- SECTION "Block's Documentation" [1862-] -->




<h1><a name="creating_state_machine_blocks" id="creating_state_machine_blocks">Creating State Machine Blocks</a></h1>
<div class="level1">

<p>

Check this <a href="/doc/creating_new_building_blocks" class="wikilink1" title="doc:creating_new_building_blocks">page</a> in order to create a new building block. Remember to choose <strong>State Machine Block</strong> template in the new building block wizard.
</p>

<p>
A State Machine block has internal behavior (State Machine), automatically generated external behavior (ESM), and optionally Java code.
This type of block is intended to be (re)used or instantiated within local blocks or system blocks.
</p>

</div>
<!-- SECTION "Creating State Machine Blocks" [1-463] -->
<h2><a name="parameter_nodes" id="parameter_nodes">Parameter Nodes</a></h2>
<div class="level2">

<p>
Since this type of block is meant to be used in other enclosing blocks, it must have parameter nodes. When a State Machine block is instantiated these nodes are referred to as pins and used to connect the instance with other modelling elements. Parameter nodes for a State Machine block are defined within the Parameter Node table:
</p>

<p>
<a href="/_detail/doc/ski_lockl_parameter.png?id=doc%3Acreating_stm_blocks" class="media" title="doc:ski_lockl_parameter.png"><img src="/_media/doc/ski_lockl_parameter.png" class="media" alt="" /></a>
</p>

<p>
As it is the case for local block, there are different Parameter Node modes available: 
</p>
<ul>
<li class="level1"><div class="li"> Starting Parameter Nodes to start a block</div>
</li>
<li class="level1"><div class="li"> Streaming Input Parameter Nodes to pass data / information to a block while it is active</div>
</li>
<li class="level1"><div class="li"> Streaming Output Parameter Nodes to pass data / information from a block while it is active</div>
</li>
<li class="level1"><div class="li"> Terminating Parameter Nodes to terminate a block</div>
</li>
</ul>

<p>

Parameter Nodes can come with type (object flow) or without type (control flow). In the above example only <em>card</em> is typed (String).
</p>

</div>
<!-- SECTION "Parameter Nodes" [464-1373] -->
<h2><a name="state_machine" id="state_machine">State Machine</a></h2>
<div class="level2">

<p>

The State Machine is specified as a transition table within the State Machine tab:
</p>

<p>
<a href="/_detail/doc/ski_lock_state_machine.png?id=doc%3Acreating_stm_blocks" class="media" title="doc:ski_lock_state_machine.png"><img src="/_media/doc/ski_lock_state_machine.png" class="media" alt="" /></a>
</p>

<p>
The State Machine describes the internal behavior of a State Machine block.
</p>

</div>

<h4><a name="choice_states" id="choice_states">Choice States</a></h4>
<div class="level4">

<p>
Each transition has a Source State and a Target State. There is an Initial State, where everything starts and a final state, in which the block terminates. Besides normal states there are also Choice States. When reaching a Choice State there are typically two or more possibilities which transition is taken next. The decision is made according to Guards. Guards are boolean Variables or methods with boolean return value. 
In this example in Choice State <em>d0</em> the method <em>isCardValid()</em> is used as Guard. In case it returns true, the next state is <em>waitingForSki</em>, otherwise it would be <em>final</em>.
</p>

</div>

<h4><a name="trigger" id="trigger">Trigger</a></h4>
<div class="level4">

<p>

A trigger indicates when a transition takes place. A trigger can be 

</p>
<ul>
<li class="level1"><div class="li"> a starting pin (STM table: “in via <em>pinName</em>”)</div>
</li>
<li class="level1"><div class="li"> an input pin (STM table: “in via <em>pinName</em>”)</div>
</li>
<li class="level1"><div class="li"> a timeout of an internal timer (STM table: “timeout <em>timerName</em>”)</div>
</li>
<li class="level1"><div class="li"> an internal event (STM table: ”<em>EVENT_NAME</em>”)</div>
</li>
</ul>

<p>

Timer and Internal Events can be created by selecting <em>New Timer</em> / <em>New Event</em> as Trigger when creating or editing a State Machine transition. An existing timer can be started or stopped by choosing “start <em>timerName</em>” or “stop <em>timerName</em>” when creating or editing a State Machine transition. This will then appear in the Actions column of this transition.
</p>

<p>
Existing timers have to be started, and started timers have to be used as trigger.
</p>

</div>

<h4><a name="actions" id="actions">Actions</a></h4>
<div class="level4">

<p>

Actions define what is happening when a transition is executed. Each transition towards a normal state may have an arbitrary number of actions. An action can be

</p>
<ul>
<li class="level1"><div class="li"> an output pin (STM table: “out <em>pinName</em>;”)</div>
</li>
<li class="level1"><div class="li"> a terminating pin (STM table: “out <em>pinName</em>;”)</div>
</li>
<li class="level1"><div class="li"> a method call (STM table: “call <em>methodName</em>;)</div>
</li>
<li class="level1"><div class="li"> a start timer action (STM table: “start <em>timerName</em>;”)</div>
</li>
<li class="level1"><div class="li"> a stop timer action (STM table: “stop <em>timerName</em>;”)</div>
</li>
</ul>

<p>

Methods that are called as actions have to be provided in the Java file of the State Machine block. Once a method with empty parameter list and void as return value is defined in the Java file, this method is offered as possible action when creating or editing a State Machine transition. When choosing it, it will appear in the Actions column of this transition.
</p>

<p>
Timers have to be created first as trigger before being able to start or stop them as Action of a transition.
</p>

</div>

<h4><a name="state_machine_and_java_code" id="state_machine_and_java_code">State Machine and Java Code</a></h4>
<div class="level4">

<p>
The State Machine is tightly coupled with Java code. The Java file of an STM block contains variables for parameter nodes with type and methods for guards and actions.
</p>

<p>
<a href="/_detail/doc/ski_lock_java_annotated.png?id=doc%3Acreating_stm_blocks" class="media" title="doc:ski_lock_java_annotated.png"><img src="/_media/doc/ski_lock_java_annotated.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "State Machine" [1374-4173] -->
<h2><a name="external_interface_esm" id="external_interface_esm">External Interface (ESM)</a></h2>
<div class="level2">

<p>

Each time the State Machine is edited, the ESM is generated automatically from the State Machine specification. 
</p>

<p>
The ESM is shown as transition table in the External tab:
</p>

<p>
<a href="/_detail/doc/ski_lock_esm.png?id=doc%3Acreating_stm_blocks" class="media" title="doc:ski_lock_esm.png"><img src="/_media/doc/ski_lock_esm.png" class="media" alt="" /></a>
</p>

<p>
Both, the State Machine and the ESM can be shown as Diagram:
</p>

<p>
<a href="/_detail/doc/ski_lock_state_machine_diagram_esm_diagram.png?id=doc%3Acreating_stm_blocks" class="media" title="doc:ski_lock_state_machine_diagram_esm_diagram.png"><img src="/_media/doc/ski_lock_state_machine_diagram_esm_diagram.png" class="media" alt="" /></a>
</p>

<p>
The ESM describes how the block looks from the outside and how it has to be used when being integrated. So it has the same purpose as for local blocks. However it is generated from the State Machine specification and does not have to be specified or changed. It can be understood as abstraction of the State Machine behavior. Depending on the State Machine, it might happen, that 2 or more State Machine states are merged into one ESM state. 

</p>

</div>
<!-- SECTION "External Interface (ESM)" [4174-] -->