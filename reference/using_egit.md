---
title: Using EGit
layout: reference
---


<h1><a name="using_egitintroduction" id="using_egitintroduction">Using EGit: Introduction</a></h1>
<div class="level1">

<p>

You may need to share some projects with your development team. Moreover, you might want discard your modifications in a project and revert back to an older version. We recommend you to use <a href="http://git-scm.com/" class="urlextern" title="http://git-scm.com/"  rel="nofollow">Git</a>, a distributed version control system that emphasizes speed and efficiency. In this page, we describe how to use <a href="http://www.eclipse.org/egit/" class="urlextern" title="http://www.eclipse.org/egit/"  rel="nofollow">EGit</a>, a Git implementation used within the Eclipse IDE, for some typical use cases.
</p>

<p>
Note that you can also install git command-line software and other <acronym title="Graphical User Interface">GUI</acronym> tools. However, we will use EGit here.
</p>

<p>
This is not a tutorial on Git. However, a short description about Git is given. The full features of EGit are not covered either.
</p>

</div>
<!-- SECTION "Using EGit: Introduction" [1-731] -->
<h2><a name="installing_egit" id="installing_egit">Installing EGit</a></h2>
<div class="level2">

<p>

If you have not installed EGit, do the following steps: 
</p>
<ul>
<li class="level1"><div class="li"> In Eclipse, select <em><strong>Help → Install New Software…</strong></em>.</div>
</li>
<li class="level1"><div class="li"> Type “egit” in the first text field in the opened window.</div>
</li>
<li class="level1"><div class="li"> Select the only option shown on the drop-down list. It should contain the update side of EGit: <strong><a href="http://download.eclipse.org/egit/updates" class="urlextern" title="http://download.eclipse.org/egit/updates"  rel="nofollow">http://download.eclipse.org/egit/updates</a></strong></div>
</li>
<li class="level1"><div class="li"> Select <strong>Eclipse EGit</strong>.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-1.jpg?id=doc%3Ausing_egit" class="media" title="doc:egit-1.jpg"><img src="/_media/doc/egit-1.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Follow the next step by clicking button <em>Next</em> until the plugin is installed.</div>
</li>
<li class="level1"><div class="li"> After the installation, restart the Eclipse IDE.</div>
</li>
</ul>

<p>

Now let us open the Git Repositories view which is used to manage repositories:
</p>
<ul>
<li class="level1"><div class="li"> Select <em>Window → Show View → Other</em></div>
</li>
<li class="level1"><div class="li"> Type “git” on the search field at the top</div>
</li>
<li class="level1"><div class="li"> Select <em>Git Repositories</em></div>
</li>
</ul>

<p>
You should see a window like the following figure.
</p>

<p>
<a href="/_detail/doc/egit-2.jpg?id=doc%3Ausing_egit" class="media" title="doc:egit-2.jpg"><img src="/_media/doc/egit-2.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Installing EGit" [732-1554] -->
<h2><a name="setting_identity" id="setting_identity">Setting Identity</a></h2>
<div class="level2">

<p>

An important thing to do before working with Git is to set your name and email which are used to identify who do changes.

</p>
<ul>
<li class="level1"><div class="li"> In Eclipse, open the <em><strong>Preferences</strong></em> window. For Mac <acronym title="Operating System">OS</acronym>, select <em><strong>Eclipse → Preferences</strong></em>. For Windows, select <em><strong>Window → Preferences</strong></em>.</div>
</li>
<li class="level1"><div class="li"> Find the Git configuration preferences by selecting <em><strong>(1) Team → Git → Configuration</strong></em> on the left hand-side list. You can also just type “git” in the filter textfield on the top left and then select “Configuration”.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-3.jpg?id=doc%3Ausing_egit" class="media" title="doc:egit-3.jpg"><img src="/_media/doc/egit-3.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Click the <em>(2) New Entry</em> button. You will get a new window like the following figure.</div>
</li>
</ul>

<p>

<a href="/_detail/doc/egit-4a.jpg?id=doc%3Ausing_egit" class="media" title="doc:egit-4a.jpg"><img src="/_media/doc/egit-4a.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Fill in the <em>Key</em> field with <em>user.name</em> and the <em>Value</em> with your name.</div>
</li>
<li class="level1"><div class="li"> Click OK.</div>
</li>
<li class="level1"><div class="li"> Click again the <em>New Entry</em> button. </div>
</li>
<li class="level1"><div class="li"> Now fill the <em>Key</em> field with <em>user.email</em> and the <em>Value</em> with your email.</div>
</li>
<li class="level1"><div class="li"> Click OK.</div>
</li>
</ul>

</div>
<!-- SECTION "Setting Identity" [1555-2471] -->
<h2><a name="git_in_a_nutshell" id="git_in_a_nutshell">Git in a Nutshell</a></h2>
<div class="level2">

<p>
If you already familiar with Git, you can skip this section. This part is not intended to describe Git in detail. Read the <a href="http://progit.org/book/" class="urlextern" title="http://progit.org/book/"  rel="nofollow">Git Pro</a> book by Scott Chacon, if you want to learn more.
</p>

<p>
Git is a Distributed Version Control System (DVCS) which handles data differently than most other VCSs. Usually, VCSs store information as a set of files and the changes made to each file over time. In Git, every repository has a complete history and full revision tracking capabilities. Fig 1-4 (How other VCSs store data) and Fig 1-5 (How Git store data) in the <a href="http://git-scm.com/book/en/Getting-Started-Git-Basics" class="urlextern" title="http://git-scm.com/book/en/Getting-Started-Git-Basics"  rel="nofollow">Git Pro</a> book illustrate this difference.
</p>

<p>
Git is also a fully distributed VCS. It does not depend on a central server nor network access.
</p>

</div>

<h4><a name="repository" id="repository">Repository</a></h4>
<div class="level4">

<p>
A repository can contain several projects. In EGit, these should be Eclipse projects and for us  projects or libraries containing building blocks. We recommend one Git repository contains one project in order to be able to maintain your projects easily. In this documentation, we assume this is the case.
</p>

<p>
In order to share a project with your development team, you need to store the content of your <strong>local</strong> repository in your machine in a remote location (a Git server or a hosting service). Obtaining a shared project is achieved by getting a copy of an <strong>upstream</strong> or a <strong>remote</strong> repository into your machine.
</p>

</div>

<h4><a name="working_directory" id="working_directory">Working Directory</a></h4>
<div class="level4">

<p>
A Git repository also contains the history of its content, i.e., a project. The Git working directory is a single checkout of one version of the project. If the project is also in your Eclipse workspace, the version in the workspace is the same as the one in the working directory.
</p>

<p>
Relations among local repository, remote repository, working directory and the Eclipse workspace can be depicted in the following figure. They will be explained further with four <a href="#typical_use_cases" title="doc:using_egit &crarr;" class="wikilink1">typical use cases</a>.
</p>

<p>

<a href="/_detail/doc/egit-5a.jpg?id=doc%3Ausing_egit" class="media" title="doc:egit-5a.jpg"><img src="/_media/doc/egit-5a.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Git in a Nutshell" [2472-4463] -->
<h2><a name="git_project_hosting_service" id="git_project_hosting_service">Git Project Hosting Service</a></h2>
<div class="level2">

<p>

You can use a hosting provider for Git projects to store a copy of your repository remotely and share it with your development team. There are several providers, e.g., <a href="https://github.com/" class="urlextern" title="https://github.com/"  rel="nofollow">Github</a> and <a href="https://bitbucket.org/" class="urlextern" title="https://bitbucket.org/"  rel="nofollow">Bitbucket</a>. Here, we use Bitbucket.
</p>

<p>
To use Bitbucket hosting service, you need to create an account.

</p>
<ul>
<li class="level1"><div class="li"> Go to the <a href="https://bitbucket.org/account/signup/" class="urlextern" title="https://bitbucket.org/account/signup/"  rel="nofollow">signup</a> page.</div>
</li>
<li class="level1"><div class="li"> Fill in the necessary information. You can use <em>Individual account</em>.</div>
</li>
</ul>

<p>

We can use HTTPS or <acronym title="Secure Shell">SSH</acronym> for the communication protocol between local repository and Bitbucket. To use HTTPS you need to supply your username and password. To use <acronym title="Secure Shell">SSH</acronym>, you need to set up an RSA key pair if you do not have them. Here, we will use HTTPS.
</p>

</div>
<!-- SECTION "Git Project Hosting Service" [4464-5234] -->
<h2><a name="typical_use_cases" id="typical_use_cases">Typical Use Cases</a></h2>
<div class="level2">

<p>

We show four cases, namely:

</p>
<ul>
<li class="level1"><div class="li"> <a href="/doc/egit_obtain_shared_project" class="wikilink1" title="doc:egit_obtain_shared_project">Obtaining a shared project</a></div>
</li>
<li class="level1"><div class="li"> <a href="/doc/egit_contributing" class="wikilink1" title="doc:egit_contributing">Contributing to a shared project</a></div>
</li>
<li class="level1"><div class="li"> <a href="/doc/egit_get_commits" class="wikilink1" title="doc:egit_get_commits">Obtaining modifications from others</a></div>
</li>
<li class="level1"><div class="li"> <a href="/doc/egit_sharing_project" class="wikilink1" title="doc:egit_sharing_project">Sharing a project</a></div>
</li>
</ul>

</div>
<!-- SECTION "Typical Use Cases" [5235-] -->