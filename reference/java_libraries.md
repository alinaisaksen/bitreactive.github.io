---
title: Java Libraries
layout: reference
---


<h1><a name="java_libraries" id="java_libraries">Java Libraries</a></h1>
<div class="level1">

<p>
The Java code of a building block may depend on libraries that come from Java archives. If you have a JAR file and want to use it within your building block, do the following:

</p>
<ol>
<li class="level1"><div class="li"> Copy the JAR file into the Eclipse project. An ideal place is a folder called “lib”, directly under the project. You may create this folder if it does not yet exist. However you decide on the location, do <strong>not</strong> copy it under the “src” folder. (One reason for not putting it under the “src” folder is that the Java build process will copy it into the binary folder, and you end up with redundant files.)</div>
</li>
<li class="level1"><div class="li"> Within the building block editor, switch to the “Overview” tab.</div>
</li>
<li class="level1"><div class="li"> Go to the Java section, and add the Jar file there. This entry tells the compiler that the building blocks needs this Jar file, and it will be copied into the generated project.</div>
</li>
<li class="level1"><div class="li"> To add the Jar file to the build path of your project as well, navigate to the file in the Package Explorer, and select <em>Build Path / Add to Build Path</em>. </div>
</li>
<li class="level1"><div class="li"> The name of the Jar file should now also appear under <em>Referenced Libraries</em>, and Java code within the project may refer to its contained types.</div>
</li>
<li class="level1"><div class="li"> In case your building block is part of a library and clients may need access to its contained types, you should the Eclipse project for the library export it as well. Right click on the project ion the Package Explorer and navigate to <em>Build Path / Order and Export</em>. Select the Jar file and check it, so it will be exported.</div>
</li>
<li class="level1"><div class="li"> If the Jar files are to be distributed under a certain license, you can also contain the license file into the project and add it to the building block, using the <em>Required Resource</em> section in the Overview page of the editor.</div>
</li>
</ol>

<p>

Some hints:

</p>
<ul>
<li class="level1"><div class="li"> The compiler analyzes dependencies of the Java code, but does only copy Java source files that reside within projects created with the <acronym title="Software Development Kit">SDK</acronym>. (This means, for instance, it does not follow project dependencies.) JAR-files are only copied if they are added in the way described above.</div>
</li>
<li class="level1"><div class="li"> Jar files must be added <strong>relative to the project</strong>, which is done best by right-clicking the Jar file in the Package Explorer and selecting <em>Build Path / Add to Build Path</em>.</div>
</li>
</ul>

</div>
<!-- SECTION "Java Libraries" [1-2225] -->
<h2><a name="license_files" id="license_files">License Files</a></h2>
<div class="level2">

<p>
If a JAR file (or any other resource) requires that it is shipped with a license file, place the license file into a folder <em>licenses</em> within the project of the building blocks. Refer to the licenses that are required for a building block on its overview page of the editor. These files are copied once a building block is part of an implementation. 
</p>

</div>
<!-- SECTION "License Files" [2226-2608] -->
<h2><a name="example" id="example">Example</a></h2>
<div class="level2">

<p>

Below are the screenshots of a building block to access Twitter. This block needs access to the two jar files <em>dom4j.jar</em> and <em>jaxen.jar</em>. These Jar files were added to the project that contains the building block, within the <em>lib</em> folder (<strong>1</strong>). They were also added to the class path of the project and are therefore listed under <em>Referenced Libraries</em> (<strong>2</strong>).  
</p>

<p>
<a href="/_detail/doc/screen_shot_2010-12-01_at_12.08.40_pm.png?id=doc%3Ajava_libraries" class="media" title="doc:screen_shot_2010-12-01_at_12.08.40_pm.png"><img src="/_media/doc/screen_shot_2010-12-01_at_12.08.40_pm.png" class="media" alt="" /></a>
</p>

<p>
To be copied during compilation, these Jar files also have to be added to the block within the Overivew Page of the editor.
</p>

<p>
<a href="/_detail/doc/screen_shot_2010-12-01_at_12.08.48_pm.png?id=doc%3Ajava_libraries" class="media" title="doc:screen_shot_2010-12-01_at_12.08.48_pm.png"><img src="/_media/doc/screen_shot_2010-12-01_at_12.08.48_pm.png" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Example" [2609-] -->