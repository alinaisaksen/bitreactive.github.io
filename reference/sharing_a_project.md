---
title: Sharing a Project with EGit
layout: reference
---


<h1><a name="sharing_a_project_with_egit" id="sharing_a_project_with_egit">Sharing a Project with EGit</a></h1>
<div class="level1">

<p>

We assume you already have a project that you want to share with your team in your Eclipse workspace. Sharing a project with EGit consists of several steps explained below.
</p>

</div>
<!-- SECTION "Sharing a Project with EGit" [1-217] -->
<h3><a name="step_1_create_an_upstream_repository" id="step_1_create_an_upstream_repository">Step 1. Create an Upstream Repository</a></h3>
<div class="level3">

<p>

First, we create a repository on Bitbucket.

</p>
<ul>
<li class="level1"><div class="li"> Go to the Bitbucket website</div>
</li>
<li class="level1"><div class="li"> Type “<strong>c</strong>” then “<strong>r</strong>”</div>
</li>
<li class="level1"><div class="li"> Provide a name for the repository. You can also use the project name.</div>
</li>
<li class="level1"><div class="li"> Choose Git for the repository type</div>
</li>
<li class="level1"><div class="li"> Click button “<strong>Create repository</strong>”.</div>
</li>
<li class="level1"><div class="li"> You will get a page similar to the following figure.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/new-repo-bitbucket2.jpg?id=doc%3Aegit_sharing_project" class="media" title="doc:new-repo-bitbucket2.jpg"><img src="/_media/doc/new-repo-bitbucket2.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Step 1. Create an Upstream Repository" [218-621] -->
<h3><a name="step_2_clone_the_upstream_repository" id="step_2_clone_the_upstream_repository">Step 2. Clone the Upstream Repository</a></h3>
<div class="level3">

<p>

Then, we copy the upstream repository to a local repository and Git working directory. This step is related to the red arrow <strong>clone</strong> from in the figure in the EGit overview <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">page</a>.

</p>
<ul>
<li class="level1"><div class="li"> Copy the repository address shown on the website. Don&#039;t include the <em>git clone</em> part</div>
</li>
<li class="level1"><div class="li"> Go to the Eclipse <acronym title="Software Development Kit">SDK</acronym>.</div>
</li>
<li class="level1"><div class="li"> Paste the repository address on the Git Repositories View. Alternatively, you can click link “<strong>Clone a Git repository</strong>”, or the icon that depicts a database and a curved arrow (see the following figure).</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-7.jpg?id=doc%3Aegit_sharing_project" class="media" title="doc:egit-7.jpg"><img src="/_media/doc/egit-7.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> You will get a window similar to the following figure.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-8.jpg?id=doc%3Aegit_sharing_project" class="media" title="doc:egit-8.jpg"><img src="/_media/doc/egit-8.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Fill in the Authentication part with your Bitbucket username and password. Also click the checkbox to store your credentials in a secure store.</div>
</li>
<li class="level1"><div class="li"> Click the Next and eventually Finish buttons until your local repository and Git working directory is created.</div>
</li>
<li class="level1"><div class="li"> In the Git Repositories View, you should get the newly created repository.</div>
</li>
</ul>

</div>
<!-- SECTION "Step 2. Clone the Upstream Repository" [622-1665] -->
<h3><a name="step_3_link_the_project_with_the_local_repository" id="step_3_link_the_project_with_the_local_repository">Step 3. Link the Project with the Local Repository</a></h3>
<div class="level3">

<p>

Next, we need connect the project to be shared in the Eclipse workspace with the Git working directory that we just created. This corresponds to the blue arrow <strong>share</strong> in the <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">figure</a> illustrating EGit.

</p>
<ul>
<li class="level1"><div class="li"> Go to the Package Explorer View.</div>
</li>
<li class="level1"><div class="li"> Right click the project that you want to share.</div>
</li>
<li class="level1"><div class="li"> Select <em><strong>Team → Share Project</strong></em>.</div>
</li>
<li class="level1"><div class="li"> You will get a new window. Then, select <strong>Git</strong> and click the <strong>Next</strong> button.</div>
</li>
<li class="level1"><div class="li"> You will see a window like the one below. <strong>(1)</strong> Select the local repository we just created from the drop-down list, and click <strong>(2)</strong> Finish.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-9.jpg?id=doc%3Aegit_sharing_project" class="media" title="doc:egit-9.jpg"><img src="/_media/doc/egit-9.jpg" class="media" alt="" /></a>
</p>

<p>
Note that the project is not yet stored in the local repository. It is now in the Git working directory.

</p>
<ul>
<li class="level1"><div class="li"> Go to the Package Explorer View.</div>
</li>
<li class="level1"><div class="li"> Right click the project that we just linked and select <em><strong>Refresh</strong></em>. You should see the question marks on several files and folders in the project.</div>
</li>
<li class="level1"><div class="li"> Go to the Git Repositories View.</div>
</li>
<li class="level1"><div class="li"> Expand the repository that is created in Step 2. Expand further the folder called <em><strong>Working Directory</strong></em></div>
</li>
<li class="level1"><div class="li"> Click the icon that indicates <em><strong>Refresh</strong></em>. It contains two curved arrows.</div>
</li>
<li class="level1"><div class="li"> You should see that the working directory contains the shared project as also depicted in the following figure.</div>
</li>
</ul>

<p>
<a href="/_detail/doc/egit-10d.jpg?id=doc%3Aegit_sharing_project" class="media" title="doc:egit-10d.jpg"><img src="/_media/doc/egit-10d.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Step 3. Link the Project with the Local Repository" [1666-3025] -->
<h3><a name="step_4_commit" id="step_4_commit">Step 4. Commit</a></h3>
<div class="level3">

<p>

The next step is to save the project in the local repository. We do this by creating a new version in the local repository, or <strong>commit</strong> in Git term. This action is depicted by the green arrow <strong>commit</strong> in the <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">figure</a> that illustrates EGit.
</p>

</div>

<h4><a name="ignore_files_gitignore" id="ignore_files_gitignore">Ignore Files (.gitignore)</a></h4>
<div class="level4">

<p>
A Reactive Blocks project contains some directories and files that are better not saved in the local repository. We can tell Git to ignore them by adding a <strong>.gitignore</strong> file in the Git working directory.

</p>
<ul>
<li class="level1"><div class="li"> Find out the location of the Git working directory. It is shown next to the Git working directory (after a dash ”-”). You can also hover your pointer to see it clearly. See the previous figure.</div>
</li>
<li class="level1"><div class="li"> In the location, create a text file named <strong>.gitignore</strong> with your favorite text editor.</div>
</li>
<li class="level1"><div class="li"> Fill with the following.</div>
</li>
</ul>
<pre class="code">
bin/
gen/
.backups/
*.class
</pre>
<ul>
<li class="level1"><div class="li"> You need to refresh the Git Repositories View again to see that the file is in the working directory.</div>
</li>
</ul>

<p>

Now, we are ready to commit. 

</p>
<ul>
<li class="level1"><div class="li"> In the Project Explorer View, right click the shared project.</div>
</li>
<li class="level1"><div class="li"> Select <em><strong>Team → Commit…</strong></em></div>
</li>
<li class="level1"><div class="li"> You will get a window like the following figure.</div>
<ol>
<li class="level2"><div class="li"> Fill in a commit message (mandatory)</div>
</li>
<li class="level2"><div class="li"> Select all files</div>
</li>
<li class="level2"><div class="li"> Click button <em>Commit</em></div>
</li>
</ol>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-11.jpg?id=doc%3Aegit_sharing_project" class="media" title="doc:egit-11.jpg"><img src="/_media/doc/egit-11.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Step 4. Commit" [3026-4352] -->
<h3><a name="step_5_push_to_upstream" id="step_5_push_to_upstream">Step 5. Push to Upstream</a></h3>
<div class="level3">

<p>

The new commit in the local repository needs to be pushed to the upstream repository. This corresponds to the golden arrow <strong>push</strong> in the <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">figure</a> showing EGit.

</p>
<ul>
<li class="level1"><div class="li"> In the Project Explorer View, right click the shared project.</div>
</li>
<li class="level1"><div class="li"> Select <em><strong>Team → Push to Upstream</strong></em>.</div>
</li>
<li class="level1"><div class="li"> You will get a window confirming the push.</div>
</li>
<li class="level1"><div class="li"> Go to Bitbucket website containing the repository. Refresh the page if necessary.</div>
</li>
</ul>

</div>

<h4><a name="note" id="note">Note</a></h4>
<div class="level4">

<p>
Depending on the version of EGit plugin you installed, the fifth step above may be done automatically by selecting to commit (executing step four).
</p>

</div>
<!-- SECTION "Step 5. Push to Upstream" [4353-4994] -->
<h3><a name="step_6_set_administrative_rights" id="step_6_set_administrative_rights">Step 6. Set Administrative Rights</a></h3>
<div class="level3">

<p>

The last step to share your project with your development team is to assign access rights to the team members or groups.

</p>
<ul>
<li class="level1"><div class="li"> In the Bitbucket website, select the setting link as shown in the following figure</div>
</li>
<li class="level1"><div class="li"> On the left hand-side list, select <em><strong>Access management</strong></em></div>
</li>
<li class="level1"><div class="li"> Grant appropriate access rights to other users or groups as needed</div>
</li>
</ul>

<p>

<a href="/_detail/doc/sharing-bitbucket.jpg?id=doc%3Aegit_sharing_project" class="media" title="doc:sharing-bitbucket.jpg"><img src="/_media/doc/sharing-bitbucket.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Step 6. Set Administrative Rights" [4995-] -->