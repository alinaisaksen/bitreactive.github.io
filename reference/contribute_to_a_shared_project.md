---
title: Contributing to a Shared Project
layout: reference
---


<h1><a name="contributing_to_a_shared_project" id="contributing_to_a_shared_project">Contributing to a Shared Project</a></h1>
<div class="level1">

<p>

Once you obtain a shared project through Git or share a project yourself, you can continue working on the project. For example, you can modify a block, create a new block, or delete an existing one. 
</p>

<p>
From time to time, you might want to store your modifications to the local repository, or do a <strong>commit</strong> in Git term. This action is typically done quite often. With Git, you can later go back to a certain commit when, e.g., you find that your modifications do not work.
</p>

<p>
Modifications to a shared project need to be pushed to the corresponding remote repository so that other people with whom the project is shared can get them. This is done in two steps explained below.
</p>

</div>
<!-- SECTION "Contributing to a Shared Project" [1-724] -->
<h3><a name="step_1_commit" id="step_1_commit">Step 1. Commit</a></h3>
<div class="level3">

<p>

Commit means creating a version of your project in the local repository. This corresponds to the green arrow <strong>commit</strong> in the EGit illustrating <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">figure</a>.
</p>

<p>
To do a commit, follow these steps:

</p>
<ul>
<li class="level1"><div class="li"> In the Project Explorer View, right click the shared project. Usually, the project has a <strong>&gt;</strong> mark in front of the name. This indicates that there are modifications which have not been committed.</div>
</li>
<li class="level1"><div class="li"> Select <em><strong>Team → Commit…</strong></em></div>
</li>
<li class="level1"><div class="li"> You will get a window like the following figure.</div>
<ol>
<li class="level2"><div class="li"> Fill in a commit message (mandatory)</div>
</li>
<li class="level2"><div class="li"> Remember to start tracking newly created files</div>
</li>
<li class="level2"><div class="li"> Click button Commit</div>
</li>
</ol>
</li>
</ul>

<p>
<a href="/_detail/doc/egit-19.jpg?id=doc%3Aegit_contributing" class="media" title="doc:egit-19.jpg"><img src="/_media/doc/egit-19.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Step 1. Commit" [725-1414] -->
<h3><a name="step_2_push_to_upstream" id="step_2_push_to_upstream">Step 2. Push to Upstream</a></h3>
<div class="level3">

<p>

Push means storing commit(s) to an upstream repository. This corresponds to the golden arrow <strong>push</strong> in the <a href="/doc/using_egit#working_directory" class="wikilink1" title="doc:using_egit">figure</a> illustrating EGit.
</p>

<p>
Note that you may push several commits at once.
</p>

<p>
To push commit(s) to an upstream repository, follow these steps:

</p>
<ul>
<li class="level1"><div class="li"> In the Project Explorer View, right click the shared project.</div>
</li>
<li class="level1"><div class="li"> Select <em><strong>Team → Push to Upstream</strong></em>.</div>
</li>
<li class="level1"><div class="li"> You will get a window that confirms the push.</div>
</li>
<li class="level1"><div class="li"> Go to the Bitbucket website that contains the repository.</div>
</li>
<li class="level1"><div class="li"> You should see your commit(s) have been saved. Refresh if necessary.</div>
</li>
</ul>

</div>
<!-- SECTION "Step 2. Push to Upstream" [1415-2036] -->
<h3><a name="note" id="note">Note</a></h3>
<div class="level3">

<p>

Depending on the version of EGit plugin you installed, the second step above may be done automatically by selecting to commit (executing step one).
</p>

</div>
<!-- SECTION "Note" [2037-] -->