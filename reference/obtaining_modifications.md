---
title: Obtaining Modifications
layout: reference
---


<h1><a name="obtaining_modifications_from_others" id="obtaining_modifications_from_others">Obtaining Modifications from Others</a></h1>
<div class="level1">

<p>

In a shared project, other people with whom the project is shared can make some changes, for example, modify a block, create a new block, or delete an existing one. Their modifications are stored as commits on the remote repository. In the following, we describe how to obtain those modifications.
</p>

</div>
<!-- SECTION "Obtaining Modifications From Others" [1-352] -->
<h3><a name="step_1_fetch_from_upstream" id="step_1_fetch_from_upstream">Step 1. Fetch From Upstream</a></h3>
<div class="level3">

<p>

First, we need to get the commits to our local repository. This corresponds to the red arrow <strong>fetch</strong> in the <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">figure</a> illustrating EGit.
</p>

<p>
Follow these steps:

</p>
<ul>
<li class="level1"><div class="li"> In the Git Repositories View, right click the repository containing the shared project.</div>
</li>
<li class="level1"><div class="li"> Select <em><strong>Fetch From Upstream</strong></em></div>
</li>
<li class="level1"><div class="li"> After sometime, you will get a confirmation window that also shows how many commits are fetched.</div>
</li>
</ul>

</div>
<!-- SECTION "Step 1. Fetch From Upstream" [353-819] -->
<h3><a name="step_2_merge" id="step_2_merge">Step 2. Merge</a></h3>
<div class="level3">

<p>

Then, in order to get the modification into your Eclipse workspace (which also means into the Git working directory the workspace is connected to), we need to merge them to our current checkout version in the working directory. This action is called <strong>merge</strong> in Git term. It 
corresponds to the golden arrow <strong>merge</strong> in the <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">figure</a> illustrating EGit.
</p>

<p>
Follow these steps:

</p>
<ul>
<li class="level1"><div class="li"> In the Git Repositories, right click the repository containing the shared project.</div>
</li>
<li class="level1"><div class="li"> Select <em><strong>Merge</strong></em>.</div>
</li>
<li class="level1"><div class="li"> You will get a window similar to the following figure.</div>
<ol>
<li class="level2"><div class="li"> Expand folder <strong>Remote Tracking</strong> and select branch <strong>origin/master</strong></div>
</li>
<li class="level2"><div class="li"> Click button <strong>Merge</strong></div>
</li>
</ol>
</li>
</ul>

<p>
<a href="/_detail/doc/egit-20.jpg?id=doc%3Aegit_get_commits" class="media" title="doc:egit-20.jpg"><img src="/_media/doc/egit-20.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> You will get a window showing the result of the merge action.</div>
</li>
</ul>

</div>
<!-- SECTION "Step 2. Merge" [820-1622] -->
<h3><a name="note" id="note">Note</a></h3>
<div class="level3">

<p>

By choosing command <strong>Pull</strong> instead of <strong>Fetch from Upstream</strong>, the second step will be executed automatically.
</p>

</div>
<!-- SECTION "Note" [1623-] -->