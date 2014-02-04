---
title: Sessions Overview
layout: reference
---


<h1><a name="multiplicity_of_blocks_and_sessions" id="multiplicity_of_blocks_and_sessions">Sessions Overview</a></h1>
<div class="level1">

<p>
Usually, each building block is instantiated once, as you would probably expect. But besides this normal case, there are some other multiplicity patterns (or session patterns) that are possible, and that allow to handle various cases:

</p>
<ul>
<li class="level1"><div class="li"> <strong>Normal:</strong> A block with a <em>normal</em> session type is instantiated once.</div>
</li>
<li class="level1"><div class="li"> <strong>Multi-session</strong>: A block with a multi-session can be executed with multiple sessions at the same time, and each sessions executed independently of the others. This is useful when one needs to keep track of several instances of devices, users, or other processes that are easier to handle separately.</div>
</li>
<li class="level1"><div class="li"> <strong>Single-Session</strong>: A block with a <em>single-session</em> is also instantiated exactly once, but it is realized as its own state machine, which is useful if a combined state machine in the normal case would be too complex. </div>
</li>
<li class="level1"><div class="li"> <strong>Singleton</strong>: A singleton block exists as exactly one instance in the entire system, although several other building blocks may refer to it. This is useful if we need a resource that exists only once in the system (for example, a communication channel), and that should be shared among several other blocks.</div>
</li>
</ul>

<p>
The different session types have a different syntax:
</p>

<p>
<a href="/_detail/doc/session-types.png?id=doc%3Amultipicity_of_blocks" class="media" title="doc:session-types.png"><img src="/_media/doc/session-types.png" class="media" alt="" /></a>
</p>

<p>

Depending on the session type, communication with the session works differently:
</p>
<ul>
<li class="level1"><div class="li"> <strong>Normal</strong> sessions are integrated with the surrounding block, so that the communication via the pins is <strong>synchronous</strong>. This means that a run-to-completion step may cross the border of the blocks, even several times, and is not interrupted or buffered.</div>
</li>
<li class="level1"><div class="li"> <strong>Multi-sessions</strong>, <strong>single-sessions</strong>, and <strong>singletons</strong> are implemented separately from the surrounding block, and therefore the communication is buffered. This means that steps cannot continue directly when they enter or exit a block, but are interrupted. </div>
</li>
</ul>

</div>
<!-- SECTION "Multiplicity of Blocks and Sessions" [3-1903] -->
<h2><a name="setting_the_session_type_when_using_a_block" id="setting_the_session_type_when_using_a_block">Setting the Session Type when Using a Block</a></h2>
<div class="level2">

<p>

When <strong>using</strong> a block, you may in some cases select among different session type.
Right-click the block and select the session type. Depending on how the block is constructed, different session types may be available. 
If blocks are designed and optimized for a fixed session type, they may be initialized with that session type right away, so you do not have to worry about it. 
</p>

<p>

<a href="/_detail/doc/session-selection-1.png?id=doc%3Amultipicity_of_blocks" class="media" title="doc:session-selection-1.png"><img src="/_media/doc/session-selection-1.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Setting the Session Type when Using a Block" [1904-2380] -->
<h2><a name="setting_the_session_type_when_creating_a_block" id="setting_the_session_type_when_creating_a_block">Setting the Session Type when Creating a Block</a></h2>
<div class="level2">

<p>
When you create a building block, you can select as which kind of session type it may be used. This is usually a good idea, since it it often clear in which session type a block should be used anyways. In addition, with the session type set, the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> can execute additional inspection and find more errors. 
</p>

<p>
To determine the session type, go to the overview page of the editor, and choose the session pattern from the combo box.
</p>

<p>
<a href="/_detail/doc/session-selection-2.png?id=doc%3Amultipicity_of_blocks" class="media" title="doc:session-selection-2.png"><img src="/_media/doc/session-selection-2.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Setting the Session Type when Creating a Block" [2381-] -->




<h1><a name="using_multi-session_blocks" id="using_multi-session_blocks">Using Multi-Session Blocks</a></h1>
<div class="level1">

<p>

Multi-session blocks execute several instances of a block in parallel. This is useful when you need to keep track of several things in the real world at the same time. 
</p>

<p>
For example, if you would like to keep track of an entire fleet of vehicles at the same time, you need to create a data structure that keeps track of each vehicle. A multi-session block gives you such a data structure. In addition (and that’s the most useful part), you can define behavior that is executed for each of the session instances in separately. For example, each vehicle can have its own timers and other building blocks to monitor and control it, and they are all working independently of each other.
</p>

<p>
The session instances are created dynamically, while the application is running. There can be as many instances as you need, and they can be created and terminated at any time. Internally, multi-session blocks can be made of any number and kind of building block. 
</p>

<p>
Multi-session blocks can contain very simple logic, but also complete sub-systems. Multi-session blocks may also contain further multi-session blocks. 
</p>

<p>
You can think of a multi-session block as a stack of cards, where each instance corresponds to one card. That is symbolized by the extra border around multi-session blocks.
</p>

</div>
<!-- SECTION "Using Multi-Session Blocks" [1-1322] -->
<h2><a name="using_multi-instance_blocks" id="using_multi-instance_blocks">Using Multi-Instance Blocks</a></h2>
<div class="level2">

<p>
By using multi-session blocks we mean that you integrate an existing multi-session block (for example one from a library) into your application.
</p>

<p>
Of course, whenever we work with several instances of something, we need to somehow distinguish the instances from each other. This is taken care of by the internal logic of the multi-session block. Therefore, when using a multi-session block, there is nothing specific that we have to worry about, and the different parameters do different stuff with the instances:
</p>

<p>
<strong>Starting parameters</strong> are used to create new session instances. Like with other blocks, there can be either one simple starting parameter, or several alternative ones. Each parameter passing creates a single session instance. 
</p>

<p>
While instances of a multi-session blocks are active and running, you can pass data into them using <strong>streaming parameters</strong>. In contrast to normal blocks, multi-session blocks have an annotation that reveal more about which instances will receive the parameter, that is, “all”, “some” or exactly “one”.
</p>

<p>
Multi-session blocks may also have <strong>output parameters</strong>. These work in the same way as output parameters of other blocks, since they are always sent by one specific instance.
</p>

<p>
Since all session instances are executed separately from each other, the communication from an application and towards a multi-session block is buffered. This means that a run-to-completion step always ends at an input parameter of a multi-session block, and a new run-to-completion steps is triggered later on inside the block. The same holds for output parameters of a multi-session block, just vice-versa. (Read more on run-to-completion steps <a href="/doc/semantics" class="wikilink1" title="doc:semantics">here</a>.)
</p>

</div>
<!-- SECTION "Using Multi-Instance Blocks" [1323-3077] -->
<h2><a name="patterncreating_a_fixed_set_of_multi-session_instances" id="patterncreating_a_fixed_set_of_multi-session_instances">Pattern: Creating a Fixed Set of Multi-Session Instances</a></h2>
<div class="level2">

<p>

A new instance of a multi-session is created each time a token passes the starting parameter. The incoming parameter node needs to provide the session with its alias, which can be used to identify it. 
</p>

<p>
To create a fixed number of session instances, you can use the block <em>Constructor</em>. With its instance parameters it can be configured to issue a number of strings consisting of a prefix, a running integer and a suffix. 
</p>

<p>
<a href="/_detail/doc/constructor-for-sessions.jpg?id=doc%3Ausing-multi-sessions" class="media" title="doc:constructor-for-sessions.jpg"><img src="/_media/doc/constructor-for-sessions.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Pattern: Creating a Fixed Set of Multi-Session Instances" [3078-3615] -->
<h2><a name="patterndetecting_session_termination_consistently" id="patterndetecting_session_termination_consistently">Pattern: Detecting Session Termination Consistently</a></h2>
<div class="level2">

<p>

To be sure that a shutdown happens only after all sessions have terminated, you can use an allocator block that keeps track of all session instances, as shown below.
</p>

<p>
<a href="/_detail/doc/multi-session-with-allocator.jpg?id=doc%3Ausing-multi-sessions" class="media" title="doc:multi-session-with-allocator.jpg"><img src="/_media/doc/multi-session-with-allocator.jpg" class="media" alt="" /></a>
</p>

<p>
This example works as follows:
</p>
<ol>
<li class="level1"><div class="li"> The constructor first creates a number of sessions by passing a newly created string through the allocator towards the session. Since all strings are unique, the allocator emits them via <em>created</em>, so that new sessions are created via the starting pin.</div>
</li>
<li class="level1"><div class="li"> Once the constructor is finished, it invokes <em>stop</em> of the allocator, to tell that the system is interested in stopping once all sessions terminated. (This can in a real application be any other event that may require the system to stop, it does not have to come from the constructor.)</div>
</li>
<li class="level1"><div class="li"> The sessions in this example terminate on their own by an internal timeout. Once they terminate, they deliver their alias String to the allocator. The allocator keeps track of the remaining sessions and terminates once the last session ended.</div>
</li>
</ol>

</div>
<!-- SECTION "Pattern: Detecting Session Termination Consistently" [3616-] -->




<h1><a name="using_singleton_blocks" id="using_singleton_blocks">Using Singleton Blocks</a></h1>
<div class="level1">

<p>

A singleton block is used to consistently handle a single centralized resource (e.g.,communication channel) which needs to be shared among several blocks in an application.
</p>

<p>
In a system, there exists exactly one instance of a singleton block. You can, however, drag-and-drop a singleton block multiple times and connect them to other blocks. The Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> will consider the singleton blocks of the same name as the same instance.
</p>

<p>
A singleton block has dual <a href="/doc/esm_basic" class="wikilink1" title="doc:esm_basic">external interfaces (ESMs)</a>: 
</p>
<ul>
<li class="level1"><div class="li"> <strong>Client</strong> ESM that describes the behavior of the singleton block towards its surrounding block.</div>
</li>
<li class="level1"><div class="li"> <strong>Provider</strong> ESM which takes into account the possibility that there exists other singleton blocks of the same name in another part of a system block.</div>
</li>
</ul>

<p>

Consequently, a client ESM is simpler than a provider ESM. 
</p>

<p>
When using a singleton block you only need to take into account the simple one, i.e., the <strong><em>Client ESM</em></strong>. Moreover, you don&#039;t need to consider that other singleton blocks of the same name exist. With its client ESM, a singleton block can be treated as a normal local block.
</p>

<p>
The rest of this page shows an example of a singleton block, its usage and about data to and from the block. Another example of a singleton block is given in the <a href="/tutorial/latitude-app" class="wikilink1" title="tutorial:latitude-app">Location Application tutorial</a>.
</p>

</div>
<!-- SECTION "Using Singleton Blocks" [1-1370] -->
<h2><a name="an_examplesingleton_block_sender" id="an_examplesingleton_block_sender">An Example: Singleton Block Sender</a></h2>
<div class="level2">

<p>

The following figure depicts an example of a singleton block with its client ESM.
</p>

<p>
<a href="/_detail/doc/singleton-example.jpg?id=doc%3Ausing-singleton" class="media" title="doc:singleton-example.jpg"><img src="/_media/doc/singleton-example.jpg" class="media" alt="" /></a>
</p>

<p>
As shown by its Client ESM, the singleton block Sender can receive a message to be sent via pin <em>send</em>. Thereafter, a <em>report</em> about the message transmission can be emitted by the block, or, is &#039;delayed&#039; while a code is requested via pin <em>reqCode</em> instead.
For the latter option, the result is reported when a <em>code</em> if received by the block. The request may be denied by sending an event via pin <em>cancelled</em>.
</p>

<p>
It is important to note that the Client ESM also shows that the singleton block can only handle one send event at a time. Subsequent send event can be received after the previous is handled.
</p>

</div>
<!-- SECTION "An Example: Singleton Block Sender" [1371-2147] -->
<h2><a name="an_exampleusing_singleton_block_sender" id="an_exampleusing_singleton_block_sender">An Example: Using Singleton Block Sender</a></h2>
<div class="level2">

<p>

In order to use a singleton block you need to fulfill its client ESM. The upper part of the figure below shows an example of using the singleton block <em>Sender</em>.
</p>

<p>
<a href="/_detail/doc/using-a-singleton.jpg?id=doc%3Ausing-singleton" class="media" title="doc:using-a-singleton.jpg"><img src="/_media/doc/using-a-singleton.jpg" class="media" alt="" /></a>
</p>

<p>
Here, the block <em>Client</em> and <em>Get Code</em> respect the Client ESM of singleton block <em>Sender</em> since data from block <em>Client</em> enters the singleton block one after another one is handled.
</p>

<p>
This is illustrated by the ESM of block <em>Client</em> shown at the bottom part of the above figure. An event via pin <em>data</em> is emitted when the block is in state <em>idle</em>. The state is reached via an initial transition <em>start</em>/ or when event <em>ready</em> is received.
</p>

<p>
Further, by traversing the flows to pin <em>ready</em> in the upper part of the previous figure, we see that event <em>ready</em> follows either a token from pin <em>report</em> form the singleton block <em>Sender</em> or a token from pin <em>cancel</em> from block <em>Get Code</em>. Both alternatives bring the singleton block to a final state; the first option through pin <em>report</em> while the second one via pin <em>cancelled</em> which receives a token from the pin <em>cancel</em> of block <em>Get Code</em>.
</p>

</div>
<!-- SECTION "An Example: Using Singleton Block Sender" [2148-3328] -->
<h2><a name="sendingreceiving_events_tofrom_a_singleton" id="sendingreceiving_events_tofrom_a_singleton">Sending/Receiving Events to/from a Singleton</a></h2>
<div class="level2">

<p>

As you may notice from the figure above, all the pins of a singleton block are of type <strong><em>SingletonData</em></strong>. 
</p>

<p>
A <em>SingletonData</em> object contains:
</p>
<ul>
<li class="level1"><div class="li"> addressing information that is required for the singleton to send an event to its surrounding</div>
</li>
<li class="level1"><div class="li"> data that is sent to or received from a singleton</div>
</li>
</ul>

<p>

When using a singleton block you do not need to pay attention to the addressing part. 
</p>

<p>
To send data to a singleton block, you can create an object of type SingletonData with a parameter as illustrated in the following example.
</p>
<pre class="code Java">  <a href="http://www.google.com/search?hl=en&amp;q=allinurl%3Astring+java.sun.com&amp;btnI=I%27m%20Feeling%20Lucky"><span class="kw3">String</span></a> message <span class="sy0">=</span> <span class="st0">&quot;Hi there!&quot;</span><span class="sy0">;</span>
  SingletonData send <span class="sy0">=</span> <span class="kw1">new</span> SingletonData<span class="br0">&#40;</span>message<span class="br0">&#41;</span><span class="sy0">;</span></pre>

<p>
If no data is required to be sent to a singleton block, simply create an object without parameter.
</p>
<pre class="code Java">  SingletonData cancelled <span class="sy0">=</span> <span class="kw1">new</span> SingletonData<span class="br0">&#40;</span><span class="br0">&#41;</span><span class="sy0">;</span></pre>

<p>
To get data from the singleton block, you can use the <code>getData()</code> method as shown in the following example.
</p>
<pre class="code Java">  <span class="kw1">public</span> <span class="kw4">void</span> displayReport<span class="br0">&#40;</span>SingletonData sd<span class="br0">&#41;</span> <span class="br0">&#123;</span>
    <span class="kw1">if</span> <span class="br0">&#40;</span>sd.<span class="me1">getData</span><span class="br0">&#40;</span><span class="br0">&#41;</span> <span class="kw1">instanceof</span> Report<span class="br0">&#41;</span> <span class="br0">&#123;</span>
      Report report <span class="sy0">=</span> <span class="br0">&#40;</span>Report<span class="br0">&#41;</span> sd.<span class="me1">getData</span><span class="br0">&#40;</span><span class="br0">&#41;</span><span class="sy0">;</span>
      <a href="http://www.google.com/search?hl=en&amp;q=allinurl%3Asystem+java.sun.com&amp;btnI=I%27m%20Feeling%20Lucky"><span class="kw3">System</span></a>.<span class="me1">out</span>.<span class="me1">println</span><span class="br0">&#40;</span><span class="st0">&quot;Sending result: &quot;</span> <span class="sy0">+</span> report.<span class="me1">getResult</span><span class="br0">&#40;</span><span class="br0">&#41;</span><span class="br0">&#41;</span><span class="sy0">;</span>
      <a href="http://www.google.com/search?hl=en&amp;q=allinurl%3Asystem+java.sun.com&amp;btnI=I%27m%20Feeling%20Lucky"><span class="kw3">System</span></a>.<span class="me1">out</span>.<span class="me1">println</span><span class="br0">&#40;</span><span class="st0">&quot;Report message: &quot;</span> <span class="sy0">+</span> report.<span class="me1">getMessage</span><span class="br0">&#40;</span><span class="br0">&#41;</span><span class="br0">&#41;</span><span class="sy0">;</span>
    <span class="br0">&#125;</span>
  <span class="br0">&#125;</span></pre>

<p>
To find out which type of object is expected by (or given out from) a singleton block, check the  <strong>Parameter Nodes</strong> part in the <a href="/doc/the_arctis_editor" class="wikilink1" title="doc:the_arctis_editor">Documentation</a> page. The following figure shows the objects required and provided by the singleton block <em>Sender</em>.
</p>

<p>
<a href="/_detail/doc/singleton-data.jpg?id=doc%3Ausing-singleton" class="media" title="doc:singleton-data.jpg"><img src="/_media/doc/singleton-data.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Sending/Receiving Events to/from a Singleton" [3329-] -->