---
title: Obtaining a Shared Project
layout: reference
---


<h1><a name="obtaining_a_shared_project_with_egit" id="obtaining_a_shared_project_with_egit">Obtaining a Shared Project with EGit</a></h1>
<div class="level1">

<p>
To get a project with Git, you need the address of a remote repository containing the project and a read access to the repository. Here, we assume that the repository is hosted in Bitbucket.
</p>

</div>
<!-- SECTION "Obtaining a Shared Project with EGit" [1-244] -->
<h3><a name="step_0_locate_the_address_of_the_remote_upstream_repository" id="step_0_locate_the_address_of_the_remote_upstream_repository">Step 0. Locate the Address of the Remote (Upstream) Repository</a></h3>
<div class="level3">

<p>

If you have access to a repository in Bitbucket hosting service, you can find its address on the Bitbucket website.

</p>
<ul>
<li class="level1"><div class="li"> Go to the repository page on the Bitbucket website.</div>
</li>
<li class="level1"><div class="li"> Copy the repository address shown on the website.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/bitbucket-repaddr.jpg?id=doc%3Aegit_obtain_shared_project" class="media" title="doc:bitbucket-repaddr.jpg"><img src="/_media/doc/bitbucket-repaddr.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Step 0. Locate the Address of the Remote (Upstream) Repository" [245-579] -->
<h3><a name="step_1_clone_the_repository" id="step_1_clone_the_repository">Step 1. Clone the Repository</a></h3>
<div class="level3">

<p>

We need to copy the content of the remote repository into a local repository and its Git working directory. This step is related to the red arrow <strong>clone</strong> from in the figure in the EGit overview <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">page</a>.

</p>
<ul>
<li class="level1"><div class="li"> Copy the repository address shown on the website.</div>
</li>
<li class="level1"><div class="li"> Go to the Eclipse <acronym title="Software Development Kit">SDK</acronym>.</div>
</li>
<li class="level1"><div class="li"> Paste the repository address on the Git Repositories View. Alternatively, you can click link “Clone a Git repository”, or the icon that depicts a database and a curved arrow (see the following figure).</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-7.jpg?id=doc%3Aegit_obtain_shared_project" class="media" title="doc:egit-7.jpg"><img src="/_media/doc/egit-7.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> You will get a window similar to the following figure.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-17.jpg?id=doc%3Aegit_obtain_shared_project" class="media" title="doc:egit-17.jpg"><img src="/_media/doc/egit-17.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> <strong>(1)</strong> The address of the remote repository should already be filled.</div>
</li>
<li class="level1"><div class="li"> <strong>(2)</strong> Fill in the Authentication part with your Bitbucket username and password. Also click the checkbox to store your credentials in a secure store.</div>
</li>
<li class="level1"><div class="li"> <strong>(3)</strong> Click the Next and eventually Finish buttons until your local repository and working directory is created.</div>
</li>
<li class="level1"><div class="li"> In the Git Repositories View, you should get the newly created repository as also depicted in the figure below.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-18.jpg?id=doc%3Aegit_obtain_shared_project" class="media" title="doc:egit-18.jpg"><img src="/_media/doc/egit-18.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Step 1. Clone the Repository" [580-1746] -->
<h3><a name="step_2_import_the_project_into_the_eclipse_workspace" id="step_2_import_the_project_into_the_eclipse_workspace">Step 2. Import the Project into the Eclipse Workspace</a></h3>
<div class="level3">

<p>

To work with the project, we need to import it into the Eclipse workspace. This step corresponds to the green arrow <strong>import</strong> in the <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">figure</a> that depicts EGit.

</p>
<ul>
<li class="level1"><div class="li"> In the Git Repositories View, select the local repository containing the shared project.</div>
</li>
<li class="level1"><div class="li"> Right click and select <em><strong>Import Projects…</strong></em></div>
</li>
<li class="level1"><div class="li"> Then on the popped up window, select <strong>Finish</strong></div>
</li>
<li class="level1"><div class="li"> Your Eclipse workspace should now contain the shared project, both in the Package Explorer View and also in the Blocks View.</div>
</li>
</ul>

</div>
<!-- SECTION "Step 2. Import the Project into the Eclipse Workspace" [1747-] -->