---
title: Activity Nodes
layout: reference
---


<h1><a name="importing_libraries_and_examples" id="importing_libraries_and_examples">Importing Libraries and Examples</a></h1>
<div class="level1">

<p>

From within the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym>, you can directly import libraries and example projects to work with.
</p>

<p>
Since downloading new libraries may also update and replace existing ones, all open <a href="/doc/the_arctis_editor" class="wikilink1" title="doc:the_arctis_editor">Reactive Blocks editors</a> should be closed.
</p>
<ol>
<li class="level1"><div class="li"> In the building block view, select the import icon. <a href="/_detail/doc/discovery4.jpg?id=doc%3Adiscovery" class="media" title="doc:discovery4.jpg"><img src="/_media/doc/discovery4.jpg" class="media" alt="" /></a></div>
<ul>
<li class="level2"><div class="li"> Or click File - Import in Eclipse menu and choose “Import existing Libraries, Projects and Building Blocks” under Reactive Blocks <a href="/_detail/doc/import_file_menu.png?id=doc%3Adiscovery" class="media" title="doc:import_file_menu.png"><img src="/_media/doc/import_file_menu.png" class="media" alt="" /></a></div>
</li>
</ul>
</li>
<li class="level1"><div class="li"> If you have not signed in, you will be asked to do so. <a href="/_detail/doc/discovery-2.jpg?id=doc%3Adiscovery" class="media" title="doc:discovery-2.jpg"><img src="/_media/doc/discovery-2.jpg" class="media" alt="" /></a></div>
<ul>
<li class="level2"><div class="li"> Choose the login provider you used when you signed up and click button <em>Sign in…</em>. A browser opens, sign in with your account (if you haven&#039;t done so) and give authorization to the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym>. After you see that you signed in successfully in your browser, switch back to Eclipse. <a href="/_detail/doc/logged-in2.jpg?id=doc%3Adiscovery" class="media" title="doc:logged-in2.jpg"><img src="/_media/doc/logged-in2.jpg" class="media" alt="" /></a></div>
</li>
<li class="level2"><div class="li"> Select <em>create an account</em> or go <a href="http://blocks.bitreactive.com/login/signup.html" class="urlextern" title="http://blocks.bitreactive.com/login/signup.html"  rel="nofollow">here</a> if you have not registered before.</div>
</li>
</ul>
</li>
<li class="level1"><div class="li"> Select the libraries you want to download. Dependencies (other libraries/projects used by the downloaded libraries) are retrieved automatically. <a href="/_detail/doc/discovery3.jpg?id=doc%3Adiscovery" class="media" title="doc:discovery3.jpg"><img src="/_media/doc/discovery3.jpg" class="media" alt="" /></a></div>
</li>
<li class="level1"><div class="li"> Click <em>Next</em> to review licenses and then <em>Finish</em> button </div>
</li>
</ol>

<p>

There are two types of items you can download:
</p>
<ul>
<li class="level1"><div class="li"> <strong>Libraries</strong> (<a href="/_detail/doc/library.png?id=doc%3Adiscovery" class="media" title="doc:library.png"><img src="/_media/doc/library.png" class="media" alt="" /></a>) are provided as archives, and are downloaded read-only into a local directory, which means that you can just read them, and everything is kept consistent.</div>
</li>
<li class="level1"><div class="li"> <strong>Projects</strong> (<a href="/_detail/doc/project.gif?id=doc%3Adiscovery" class="media" title="doc:project.gif"><img src="/_media/doc/project.gif" class="media" alt="" /></a>) usually contain examples or tutorials. These are downloaded as normal Eclipse projects, in your default workspace. You can edit and change these projects.</div>
</li>
</ul>

</div>
<!-- SECTION "Importing Libraries and Examples" [1-1784] -->
<h2><a name="updating_downloaded_libraries" id="updating_downloaded_libraries">Updating Downloaded Libraries</a></h2>
<div class="level2">

<p>
Whenever you open the Discovery Wizard, it will show you which library updates are available. The figure below shows that an update for the Simple <acronym title="Hyper Text Transfer Protocol">HTTP</acronym> library is available. If your current version of the library is 1.0.1, then the newest version is 1.0.2.
</p>

<p>
<a href="/_detail/doc/lib-new-version3.jpg?id=doc%3Adiscovery" class="media" title="doc:lib-new-version3.jpg"><img src="/_media/doc/lib-new-version3.jpg" class="media" alt="" /></a>
</p>

<p>
Just select <em>Finish</em>, and updates will automatically be downloaded.
</p>

<p>
<strong>Currently, libraries should always be updated to the newest version. Older versions are deleted automatically when new ones are installed.</strong>
</p>

</div>
<!-- SECTION "Updating Downloaded Libraries" [1785-2336] -->
<h2><a name="updating_downloaded_projects" id="updating_downloaded_projects">Updating Downloaded Projects</a></h2>
<div class="level2">

<p>
Examples provided as editable projects may also be updated over time. By default, the discovery wizard <strong>does not replace</strong> your local projects, since you may want to keep some changes. 
</p>

<p>
To get the new version of projects that were downloaded, you have to <strong>rename (or delete) the old version</strong> in the Package Explorer View. Then, start the Discovery wizard again to download the new version.
</p>

</div>
<!-- SECTION "Updating Downloaded Projects" [2337-2774] -->
<h2><a name="troubleshooting" id="troubleshooting">Troubleshooting</a></h2>
<div class="level2">

<p>

In case you are not able to contact the server and download any libraries, check the following: 
</p>
<ul>
<li class="level1"><div class="li"> Are you running the newest version of the <acronym title="Software Development Kit">SDK</acronym>? If not, <a href="/doc/update_arctis" class="wikilink1" title="doc:update_arctis">please update</a>.</div>
</li>
<li class="level1"><div class="li"> Check out <a href="http://twitter.com/#!/arctis" class="urlextern" title="http://twitter.com/#!/arctis"  rel="nofollow">Twitter stream</a> where we inform about the status of our servers.</div>
</li>
<li class="level1"><div class="li"> Try to test you connection with a ping. Open the Preferences</div>
</li>
</ul>

<p>
On Windows, select <em>Window → Preferences… → Reactive Blocks → Login</em><br/>

On Mac, select <em>Eclipse → Preferences… → Reactive Blocks → Login</em>
</p>

<p>
<a href="/_detail/doc/ping.jpg?id=doc%3Adiscovery" class="media" title="doc:ping.jpg"><img src="/_media/doc/ping.jpg" class="media" alt="" /></a>

</p>

</div>
<!-- SECTION "Troubleshooting" [2775-] -->