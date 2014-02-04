---
title: Activity Nodes
layout: reference
---


<h1><a name="input_data_for_building_blocks" id="input_data_for_building_blocks">Input Data For Building Blocks</a></h1>
<div class="level1">

<p>

There are several ways in which data may be passed to a building block, all of which serve different purposes:
</p>
<ul>
<li class="level1"><div class="li"> <strong>Parameters and pins</strong> are used to pass data explicitly via a data flow into a building block.</div>
</li>
<li class="level1"><div class="li"> <strong>Instance parameters</strong> are parameterizations that apply for a specific building block <em>instance</em>, and are implemented as constant values.</div>
</li>
<li class="level1"><div class="li"> <strong>Properties</strong> are values that can be indirectly passed to a building block via a central, static map with key / value pairs.</div>
</li>
</ul>

<p>

The differences among those three mechanisms are summarized in the following figure.

</p>
<table class="inline">
	<tr class="row0">
		<td class="col0 leftalign">                      </td><th class="col1 centeralign">  Parameters and Pins  </th><th class="col2 centeralign">  Instance Parameters  </th><th class="col3 centeralign">  Properties  </th>
	</tr>
	<tr class="row1">
		<th class="col0 leftalign"> Constant value       </th><td class="col1 centeralign">  no  </td><td class="col2 centeralign">  yes  </td><td class="col3 centeralign">  changeable  </td>
	</tr>
	<tr class="row2">
		<th class="col0 leftalign"> Has default value    </th><td class="col1 centeralign">  n/a  </td><td class="col2 centeralign">  yes  </td><td class="col3 centeralign">  no  </td>
	</tr>
	<tr class="row3">
		<th class="col0 leftalign"> Scope                </th><td class="col1 centeralign">  local to block instance  </td><td class="col2 centeralign">  local to block instance  </td><td class="col3 centeralign">  shared with all block instances <br/>
within a system instance  </td>
	</tr>
	<tr class="row4">
		<th class="col0 leftalign"> When values are set  </th><td class="col1 centeralign">  n/a  </td><td class="col2 centeralign">  the block&#039;s instantiation  </td><td class="col3 centeralign">  before the values are used  </td>
	</tr>
	<tr class="row5">
		<th class="col0 leftalign"> Typical usage        </th><td class="col1 centeralign">  dynamic data  </td><td class="col2 centeralign">  data specific to <br/>
a block instance  </td><td class="col3 centeralign">  configuration data of <br/>
a system instance  </td>
	</tr>
	<tr class="row6">
		<th class="col0 leftalign"> An example           </th><td class="col1 centeralign">  an email message to be sent, <br/>
e.g., by block Send Email  </td><td class="col2 centeralign">  mail server address used, <br/>
e.g., by block Send Email  </td><td class="col3 centeralign">  Google <acronym title="Application Programming Interface">API</acronym> key identifying <br/>
an application  </td>
	</tr>
</table>

<p>

A further example is given for a building block that sends SMS that make all mechanisms to provide data to the block. See the illustrative figure below.
</p>

<p>
<a href="/_detail/doc/about-data.jpg?id=doc%3Aabout_data" class="media" title="doc:about-data.jpg"><img src="/_media/doc/about-data.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> The SMS message that includes its text and receiver is passed as data flow via parameter <em>send</em>. The text and the receiver may change every time an SMS is sent.</div>
</li>
<li class="level1"><div class="li"> An instance parameter <em>anonymizedSender</em> specifies whether the SMS should be sent with an anonymized sender. This means that all SMS messages sent via this building block instance will not be anonymized. However, there may be other instances of this block that are configured differently.</div>
</li>
<li class="level1"><div class="li"> A property is used to provide the SMS block with credentials to send an SMS using a third-party <acronym title="Application Programming Interface">API</acronym>. Such credentials are usually obtained from the <acronym title="Application Programming Interface">API</acronym> provider. In the example, the value of the property is retrieved with key <em>P-APIKEY</em> can be shared by all the instances of the block within a system instance.</div>
</li>
</ul>

<p>
Note that the type of data that is received by the building block via parameter <em>send</em> is <em>SMS</em>. In this example, this type is defined as an inner class of the Java code for the block. We can of course use basic types like <strong>int</strong>, <strong>byte</strong>, <strong>String</strong>, etc.
</p>

<p>

See this <a href="/doc/instance_parameters_for_building_blocks" class="wikilink1" title="doc:instance_parameters_for_building_blocks">page</a> to learn how to declare and set instance parameters. How to work with properties is described <a href="/doc/properties" class="wikilink1" title="doc:properties">here</a>.
</p>

</div>




<h1><a name="instance_parameters_for_building_blocks" id="instance_parameters_for_building_blocks">Instance Parameters for Building Blocks</a></h1>
<div class="level1">

<p>

<strong>Instance parameters</strong> are parameters of a building block to which values can be assigned for each building block instance. These values are constant for this building block instance, but different instances of the same building block type may have different values. 
</p>

</div>
<!-- SECTION "Instance Parameters for Building Blocks" [1-325] -->
<h2><a name="adding_instance_parameters_to_a_building_block" id="adding_instance_parameters_to_a_building_block">Adding Instance Parameters to a Building Block</a></h2>
<div class="level2">

<p>

To add or edit an instance parameter of a building block, go to the overview page within the Blocks editor. The section <em>Instance Parameters</em> lists all parameters of the block.
</p>

<p>
<a href="/_detail/doc/instance-parameter-list.png?id=doc%3Ainstance_parameters_for_building_blocks" class="media" title="doc:instance-parameter-list.png"><img src="/_media/doc/instance-parameter-list.png" class="media" alt="" /></a>
</p>

<p>
The wizard for instance parameters adds variables to the Java classes for each building block partition, and also updates the constructor of these classes. (You should never edit this constructor yourself.) 
Parameters are then accessible within the Java classes as final variables (constants).
</p>

<p>
Note that for each parameter, default values must be provided. These apply if the user of the building block does not adjust any values. These default values should be selected so that the building block executes its expected operation.
</p>

</div>
<!-- SECTION "Adding Instance Parameters to a Building Block" [326-1138] -->
<h2><a name="setting_values_on_block_instances" id="setting_values_on_block_instances">Setting Values on Block Instances</a></h2>
<div class="level2">

<p>

When a building block has instance parameters, the context menu of a call behavior action referring to it contains entry <em>Set parameters...</em>. This entry opens a dialog in which all parameter values can be set. You can also see that a building blocks has instance parameters by the little &#039;P&#039; in its upper left corner.
</p>

<p>
<a href="/_detail/doc/instance-param-set.jpg?id=doc%3Ainstance_parameters_for_building_blocks" class="media" title="doc:instance-param-set.jpg"><img src="/_media/doc/instance-param-set.jpg" class="media" alt="" /></a>
</p>

<p>
<a href="/_detail/doc/instance-param-window.jpg?id=doc%3Ainstance_parameters_for_building_blocks" class="media" title="doc:instance-param-window.jpg"><img src="/_media/doc/instance-param-window.jpg" class="media" alt="" /></a>
</p>

<p>
If parameters are not edited, default values apply.
</p>

<p>
Note that parameter instances cannot be set with values declared in the surrounding block or application, the actual values have to be provided with the specific block instance.

</p>

</div>
<!-- SECTION "Setting Values on Block Instances" [1139-] -->




<h1><a name="building_block_properties" id="building_block_properties">Building Block Properties</a></h1>
<div class="level1">

<p>

<strong>Properties</strong> are mainly intended to pass configuration data into a building block that is specific to a certain system instance. This means properties of a building block are shared among all block instances that run in the same system instance.
</p>

</div>
<!-- SECTION "Building Block Properties" [1-292] -->
<h2><a name="declaring_properties" id="declaring_properties">Declaring Properties</a></h2>
<div class="level2">

<p>

To declare a property, create a constant in the Java class for a building block that has the name of the property with a unique key.
</p>

<p>
<a href="/_detail/doc/property-example.jpg?id=doc%3Aproperties" class="media" title="doc:property-example.jpg"><img src="/_media/doc/property-example.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Declaring Properties" [293-492] -->
<h2><a name="setting_properties" id="setting_properties">Setting Properties</a></h2>
<div class="level2">

<p>

Setting properties usually happens <em>outside of</em> the building block that declared the properties.
</p>

<p>
Before a building block uses its properties, they must be set by another part of the system. Usually, all properties used by the building blocks of a system are set directly at system startup. To set a property, use the Java method <code>setProperty(key, value)</code> of the building block base class. Use the reference to the key constant as key, and pay attention to set the expected type as value.
</p>

<p>
It is allowed to pass <code>null</code> as value. Since this may happen in error, setting <code>null</code> as value appears as a warning during debugging.
</p>

<p>
<a href="/_detail/doc/property-set.jpg?id=doc%3Aproperties" class="media" title="doc:property-set.jpg"><img src="/_media/doc/property-set.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Setting Properties" [493-1185] -->
<h2><a name="getting_properties" id="getting_properties">Getting Properties</a></h2>
<div class="level2">

<p>

Getting properties happens <em>within</em> the building block that declares the properties.
</p>

<p>
To access the value of a property, use the method <code>getProperty(key)</code> of the building block base class. Not that retrieving a value that has not been set before will raise an error. You can check if a value has been set with the method <code>hasProperty(key)</code>.
</p>

<p>

<a href="/_detail/doc/property-get.jpg?id=doc%3Aproperties" class="media" title="doc:property-get.jpg"><img src="/_media/doc/property-get.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Getting Properties" [1186-] -->