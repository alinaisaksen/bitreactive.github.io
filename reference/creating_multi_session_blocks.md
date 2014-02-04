---
title: Creating Multi-Session Blocks
layout: reference
---


<h1><a name="creating_multi-session_blocks" id="creating_a_multi-session_block">Creating Multi-Session Blocks</a></h1>
<div class="level1">

</div>
<!-- SECTION "Creating a Multi-Session Block" [1-46] -->
<h3><a name="what_should_each_instance_represent" id="what_should_each_instance_represent">What Should Each Instance Represent?</a></h3>
<div class="level3">

<p>

When creating a multi-session block, you need to think first what each instance of the block should represent. For instance, if the multi-session block should keep track of orders that are delivered by a fleet of vehicles, each instance can represent a separate vehicle. But that is not the only possibility. Depending on the application, instances could also represent  an order number, or a driver. (Of course, you can also make a system that contains three multi-session blocks, one for the vehicles, one for the driver, one for each order handled by the system.)
</p>

</div>
<!-- SECTION "What Should Each Instance Represent?" [47-663] -->
<h3><a name="internal_behavior_of_a_multi-session" id="internal_behavior_of_a_multi-session">Internal Behavior of a Multi-Session</a></h3>
<div class="level3">

<p>
All session instances run independently of each other. When creating the internals of a multi-session block, you simply build a block that as if it existed only once. The internal logic of the multi-session block can be constructed like any other building block. It can contain any other type of building block that can be part of blocks, or even other multi-session blocks.
</p>

</div>
<!-- SECTION "Internal Behavior of a Multi-Session" [664-1086] -->
<h3><a name="declaring_a_multi-session" id="declaring_a_multi-session">Declaring a Multi-Session</a></h3>
<div class="level3">

<p>
Go to the Overview page of the editor, and select <strong>multi-session</strong> from the session combobox. This enables further syntactic checks for multi-sessions, and also tells all users of your block that it is intended to be used as a multi-session.
</p>

</div>
<!-- SECTION "Declaring a Multi-Session" [1087-1367] -->
<h3><a name="aliases_for_instances" id="aliases_for_instances">Aliases for Instances</a></h3>
<div class="level3">

<p>

Once it is clear what exactly an instance represent, you need to determine how the session instances should be distinguished from each other. For a fleet of vehicles, we can take for example the license plate number of each vehicle. Other good examples are email-addresses, order numbers, phone numbers, or MAC addresses. We call these identifiers aliases. (In principle, an alias is like a unique ID for each session instance. However, we call them alias, since the same alias may be used in the system by different multi-instance blocks.)
</p>

<p>
Usually it is not too hard to find sensible aliases, since in most cases, the things to distinguish already have some identifier. Of course, while an instance is active, its alias cannot be changed. If you think that you need to change an alias of a session while it is active, it is most likely that you should chose some other data as alias instead.
</p>

</div>
<!-- SECTION "Aliases for Instances" [1368-2296] -->
<h3><a name="selection_of_instances" id="selection_of_instances">Selection of Instances</a></h3>
<div class="level3">

<p>
As the only difference to normal blocks, we must describe which of the instances should receive a parameter. This means that when a parameter enters a multi-session block, we need to know which of the instances should receive a copy of the parameter. This can be one single instance, all instances, or just some selected ones. Depending on the type of input parameter, there are several possibilities:

</p>
<ul>
<li class="level1"><div class="li"> <strong>starting parameter</strong> (to one): A multi-session block needs at least one starting parameter. This parameter creates a new session instance of the block, and therefore only targets one single session. The starting parameter must also provide the alias for the session, explained below.</div>
</li>
</ul>
<ul>
<li class="level1"><div class="li"> <strong>streaming input parameter</strong> (to one) Only a single session instance will receive this parameter. Which instance that is, is determined by the incoming data type that is mapped to the alias, explained below.</div>
</li>
</ul>
<ul>
<li class="level1"><div class="li"> <strong>streaming input pin</strong> (to all) This selection option makes that all running sessions receive the parameter. </div>
</li>
</ul>
<ul>
<li class="level1"><div class="li"> <strong>streaming input pin</strong> (to some) To select some of the session, the multi-session block must implement a specific match method, further explained below.</div>
</li>
</ul>

</div>
<!-- SECTION "Selection of Instances" [2297-3513] -->
<h3><a name="declaring_the_selection_modus_one_some_or_all" id="declaring_the_selection_modus_one_some_or_all">Declaring the Selection Modus (one, some, or all)</a></h3>
<div class="level3">

<p>

Right-click on the parameter node and choose the selection mode.
</p>

<p>
<a href="/_detail/doc/selection-mode.png?id=doc%3Acreating-multi-session" class="media" title="doc:selection-mode.png"><img src="/_media/doc/selection-mode.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Declaring the Selection Modus (one, some, or all)" [3514-3670] -->
<h2><a name="sending_to_one_with_an_alias" id="sending_to_one_with_an_alias">Sending “to one” with an alias:</a></h2>
<div class="level2">

<p>

This holds both for starting parameters and for streaming parameters.
</p>

<p>
Whenever a parameter should target exactly one session, this parameter must be typed, and the type must somehow contain the alias. Since we need to pass more data into the block than just its alias, you need to declare how the alias can be extracted from an incoming parameter type. The block must therefore declare the following static method:
</p>
<pre class="code java"><span class="kw1">public</span> <span class="kw1">static</span> <a href="http://www.google.com/search?hl=en&amp;q=allinurl%3Astring+java.sun.com&amp;btnI=I%27m%20Feeling%20Lucky"><span class="kw3">String</span></a> getAlias<span class="br0">&#40;</span> ...  <span class="br0">&#41;</span> <span class="br0">&#123;</span>
...
<span class="br0">&#125;</span></pre>

<p>
The argument of this method must have the same type as the type of the incoming parameter. For instance, if the incoming parameter is of type DispatchOrder, then the getAlias method looks like this:
</p>
<pre class="code java"><span class="kw1">public</span> <span class="kw1">static</span> <a href="http://www.google.com/search?hl=en&amp;q=allinurl%3Astring+java.sun.com&amp;btnI=I%27m%20Feeling%20Lucky"><span class="kw3">String</span></a> getAlias<span class="br0">&#40;</span>DispatchOrder order<span class="br0">&#41;</span> <span class="br0">&#123;</span>
	<span class="kw1">return</span> order.<span class="me1">getAssignedVehicle</span><span class="br0">&#40;</span><span class="br0">&#41;</span><span class="sy0">;</span>
<span class="br0">&#125;</span></pre>

</div>
<!-- SECTION "Sending “to one” with an alias:" [3671-4515] -->
<h2><a name="sending_to_some_with_a_match_method" id="sending_to_some_with_a_match_method">Sending “to some” with a match method</a></h2>
<div class="level2">

<p>

Sending to several session instances simultaneously can be done using a match method. The block simply declares the following method:
</p>
<pre class="code java"><span class="kw1">public</span> <span class="kw4">boolean</span> match<span class="br0">&#40;</span><a href="http://www.google.com/search?hl=en&amp;q=allinurl%3Astring+java.sun.com&amp;btnI=I%27m%20Feeling%20Lucky"><span class="kw3">String</span></a> parameterName, <a href="http://www.google.com/search?hl=en&amp;q=allinurl%3Aobject+java.sun.com&amp;btnI=I%27m%20Feeling%20Lucky"><span class="kw3">Object</span></a> data<span class="br0">&#41;</span> <span class="br0">&#123;</span>
...
<span class="br0">&#125;</span></pre>

<p>
The parameter name is the name of the parameter for which the selection is called, and data is the provided input type. Based on this data, the name of the incoming parameter and any other value within the block, the session selection can be done. If the instance should receive an input, return true. In case the input parameter node is not typed, the data attribute is null.

</p>

</div>
<!-- SECTION "Sending “to some” with a match method" [4516-] -->