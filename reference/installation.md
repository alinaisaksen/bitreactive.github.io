---
title: Installation
layout: reference
---

<h1><a name="installing_the_reactive_blocks_sdk" id="installing_the_reactive_blocks_sdk">Installing the Reactive Blocks SDK</a></h1>
<div class="level1">

</div>
<!-- SECTION "Installing the Reactive Blocks SDK" [1-50] -->
<h2><a name="step_1get_a_user_account" id="step_1get_a_user_account">Step 1: Get a User Account</a></h2>
<div class="level2">

<p>

Before installation, make sure you have <a href="http://blocks.bitreactive.com/login/signup.html" class="urlextern" title="http://blocks.bitreactive.com/login/signup.html"  rel="nofollow">signed up</a>.
</p>

<p>
The Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> is provided as plugins to <a href="http://www.eclipse.org/" class="urlextern" title="http://www.eclipse.org/"  rel="nofollow">Eclipse</a>, so installing it means installing a <acronym title="Java Development Kit">JDK</acronym> (Java Developer Kit), then Eclipse and then the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym>.
</p>

</div>
<!-- SECTION "Step 1: Get a User Account" [51-391] -->
<h2><a name="step_2install_eclipse_431" id="step_2install_eclipse_431">Step 2: Install Eclipse 4.3.1</a></h2>
<div class="level2">

<p>

If you have <strong>Eclipse 4.3.1 (Kepler)</strong> already running on your machine, you may directly continue with Step 3.

</p>
<ul>
<li class="level1"><div class="li"> <a href="/install_sdk_win" class="wikilink1" title="install_sdk_win">Installation of Eclipse on Windows</a></div>
</li>
<li class="level2"><div class="li"> <a href="/install_sdk_mac" class="wikilink1" title="install_sdk_mac">Installation of Eclipse on Mac</a></div>
</li>
<li class="level2"><div class="li"> <a href="/install_sdk_linux" class="wikilink1" title="install_sdk_linux">Installation of Eclipse on Linux</a></div>
</li>
</ul>

<p>

Eclipse also runs also on other platforms, and that should be fine with the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym>, as well. See  installation instructions <a href="http://wiki.eclipse.org/Eclipse/Installation" class="urlextern" title="http://wiki.eclipse.org/Eclipse/Installation"  rel="nofollow">here</a>. Notice, however, that we focus with our support on the platforms above.
</p>

</div>
<!-- SECTION "Step 2: Install Eclipse 4.3.1" [392-991] -->
<h2><a name="step_3install_the_reactive_blocks_sdk_within_eclipse" id="step_3install_the_reactive_blocks_sdk_within_eclipse">Step 3: Install the Reactive Blocks SDK within Eclipse</a></h2>
<div class="level2">
<ul>
<li class="level1"><div class="li"> In Eclipse, open the software manager via <em><strong>Help → Install New Software…</strong></em></div>
</li>
<li class="level2"><div class="li"> Add the update site <a href="http://updates.bitreactive.com" class="urlextern" title="http://updates.bitreactive.com"  rel="nofollow">http://updates.bitreactive.com</a></div>
</li>
</ul>

<p>

<a href="/_detail/install_arctis.png?id=install_arctis" class="media" title="install_arctis.png"><img src="/_media/install_arctis.png" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Install the <acronym title="Software Development Kit">SDK</acronym></div>
</li>
</ul>

<p>

During the installation process, you might experience that the progress bar does not seem to advance for quite sometime. It is because installing the <acronym title="Software Development Kit">SDK</acronym> would also install its dependencies. Therefore, several update sites are also contacted and dependencies need to be calculated. This may take time.
</p>

<p>
In case of troubles, check the tips provided <a href="http://reference.bitreactive.com/troubleshoot-install" class="urlextern" title="http://reference.bitreactive.com/troubleshoot-install"  rel="nofollow">here</a>.
</p>

</div>
<!-- SECTION "Step 3: Install the Reactive Blocks SDK within Eclipse" [992-1671] -->
<h2><a name="step_4launch_the_sdk_and_sign_in" id="step_4launch_the_sdk_and_sign_in">Step 4: Launch the SDK and Sign In</a></h2>
<div class="level2">
<ul>
<li class="level1"><div class="li"> Restart Eclipse</div>
</li>
<li class="level2"><div class="li"> Open the Preferences </div>
</li>
</ul>

<p>
On Windows, select <em><strong>Window → Preferences… → Reactive Blocks → Login</strong></em><br/>

On Mac, select <em><strong>Eclipse → Preferences… → Reactive Blocks → Login</strong></em>
</p>

<p>
<a href="/_detail/pref-page-login.jpg?id=install_arctis" class="media" title="pref-page-login.jpg"><img src="/_media/pref-page-login.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Choose the provider you used when you registered and click button <em>Sign in...</em>. A browser opens, sign in with your account (if you haven&#039;t done so) and give authorization to the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym>. After you see that you signed in successfully in your browser, switch back to Eclipse. </div>
</li>
</ul>

<p>

<a href="/_detail/doc/logged-in2.jpg?id=install_arctis" class="media" title="doc:logged-in2.jpg"><img src="/_media/doc/logged-in2.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Step 4: Launch the SDK and Sign In" [1672-2278] -->
<h2><a name="further_steps" id="further_steps">Further Steps</a></h2>
<div class="level2">

<p>

Open the <a href="/doc/the_arctis_perspective" class="wikilink1" title="doc:the_arctis_perspective">Reactive Blocks Perspective</a>
</p>

<p>
See the links from the left pane or <a href="http://reference.bitreactive.com/" class="urlextern" title="http://reference.bitreactive.com/"  rel="nofollow">here</a> to read more about the <acronym title="Software Development Kit">SDK</acronym>. Alternatively, you can start with some <a href="http://bitreactive.com/developer/tutorials" class="urlextern" title="http://bitreactive.com/developer/tutorials"  rel="nofollow">tutorials</a>.

</p>

</div>
<!-- SECTION "Further Steps" [2279-] -->

<h1><a name="troubleshooting" id="troubleshooting">Troubleshooting</a></h1>
<div class="level1">

</div>
<!-- SECTION "Troubleshooting" [1-31] -->
<h2><a name="failed_to_install_java_on_windows" id="failed_to_install_java_on_windows">1. Failed to install Java on Windows</a></h2>
<div class="level2">

<p>
Installing Java on <strong>Windows</strong> platform is pretty straightforward. Make sure that you are login with an admin account. If you still find problems, check this <a href="http://docs.oracle.com/javase/7/docs/webnotes/install/windows/jdk-installation-windows.html" class="urlextern" title="http://docs.oracle.com/javase/7/docs/webnotes/install/windows/jdk-installation-windows.html"  rel="nofollow">page</a> or this <a href="http://docs.oracle.com/javase/7/docs/webnotes/install/windows/windows-online-installation-java-update-faq.html" class="urlextern" title="http://docs.oracle.com/javase/7/docs/webnotes/install/windows/windows-online-installation-java-update-faq.html"  rel="nofollow">faq</a> page from Oracle.
</p>

</div>
<!-- SECTION "1. Failed to install Java on Windows" [32-485] -->
<h2><a name="failed_to_extract_the_eclipse_zip_file" id="failed_to_extract_the_eclipse_zip_file">2. Failed to extract the Eclipse zip file</a></h2>
<div class="level2">

<p>
On <strong>Windows</strong>: Ensure that you have permission on the directory where you unzip the file. You can try to extract the file with a dedicated archiving tool, not the built-in wizard of the Explorer. See also <a href="http://wiki.eclipse.org/SDK_Known_Issues" class="urlextern" title="http://wiki.eclipse.org/SDK_Known_Issues"  rel="nofollow">known issues of Eclipse</a>.
</p>

</div>
<!-- SECTION "2. Failed to extract the Eclipse zip file" [486-816] -->
<h2><a name="dependencies_cannot_be_resolved_problem" id="dependencies_cannot_be_resolved_problem">3. &quot;Dependencies cannot be resolved&quot; problem</a></h2>
<div class="level2">

<p>
This problem can happen in <strong>all <acronym title="Operating System">OS</acronym> platforms</strong> when you install new software components or features, e.g., the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym>, or update existing ones using the Eclipse Update Manager. A feature may depend on other features. Therefore, when you install or update a feature, not only the update server of the main feature is contacted but also other sites hosting the dependent features.
</p>

<p>
To start, check some of the usual suspects: (Don&#039;t laugh - these things happen!)
</p>
<ul>
<li class="level1"><div class="li"> Are you connected to the internet?</div>
</li>
<li class="level2"><div class="li"> Do you have enough disk space? (Eclipse needs to store downloads temporarily.)</div>
</li>
</ul>

<p>
The Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> is about 10 <acronym title="Megabyte">MB</acronym> in size. Which other dependencies Eclipse needs to download depends on your installation. Usually, the <acronym title="Software Development Kit">SDK</acronym> and all necessary dependencies are downloaded rather quickly. We have seen in some cases, however, that the download may take some time. 
</p>

<p>
Then there are a number of more subtle things you should check:
</p>
<ul>
<li class="level1"><div class="li"> Check which version of Eclipse you are using. On <strong>Mac <acronym title="Operating System">OS</acronym> X</strong> choose <em>Eclipse –&gt; About Eclipse <acronym title="Software Development Kit">SDK</acronym></em> from the menu. On <strong>Windows</strong> choose <em>Help –&gt; About</em>. The <acronym title="Software Development Kit">SDK</acronym> requires at least Eclipse version 3.7.1 (Indigo).</div>
</li>
</ul>

<p>

<a href="/_detail/eclipse-version.jpg?id=troubleshoot-install" class="media" title="eclipse-version.jpg"><img src="/_media/eclipse-version.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Ensure that you have selected <strong>(1)</strong> <em>Contact all update sites during install to find required software</em>, so that the update manager wizard also checks other sites for required plugins.</div>
</li>
</ul>

<p>

 <a href="/_detail/contact-update-site3.jpg?id=troubleshoot-install" class="media" title="contact-update-site3.jpg"><img src="/_media/contact-update-site3.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Check if Eclipse can access update sites for the Indigo releases. In the update manager wizard, click <strong>(2)</strong> <em>Available Software Sites</em>. Then, check that the following two update sites are enabled:</div>
<ul>
<li class="level4"><div class="li"> <a href="http://download.eclipse.org/eclipse/updates/3.7" class="urlextern" title="http://download.eclipse.org/eclipse/updates/3.7"  rel="nofollow">http://download.eclipse.org/eclipse/updates/3.7</a></div>
</li>
<li class="level4"><div class="li"> <a href="http://download.eclipse.org/releases/indigo" class="urlextern" title="http://download.eclipse.org/releases/indigo"  rel="nofollow">http://download.eclipse.org/releases/indigo</a> </div>
</li>
</ul>
</li>
</ul>

<p>

<a href="/_detail/preferences.png?id=troubleshoot-install" class="media" title="preferences.png"><img src="/_media/preferences.png" class="media" alt="" /></a>
</p>

<p>
For each of the listed updates sites above, do the following:
</p>
<ul>
<li class="level1"><div class="li"> Select the update site in the table</div>
</li>
<li class="level1"><div class="li"> Press the <strong>Reload</strong> button </div>
</li>
</ul>

<p>
Eclipse tries to access the software site again. If the update site is not accessible, you have at least found one reason why the installation failed. If you have checked all of the points above:
</p>
<ul>
<li class="level1"><div class="li"> Try again later, in case the update site is temporarily offline</div>
</li>
<li class="level1"><div class="li"> Check our <a href="http://twitter.com/#!/arctis" class="urlextern" title="http://twitter.com/#!/arctis"  rel="nofollow">Twitter Stream</a> for any server problems</div>
</li>
<li class="level1"><div class="li"> Contact us via <a href="mailto:&#x73;&#x75;&#x70;&#x70;&#x6f;&#x72;&#x74;&#x40;&#x62;&#x69;&#x74;&#x72;&#x65;&#x61;&#x63;&#x74;&#x69;&#x76;&#x65;&#x2e;&#x63;&#x6f;&#x6d;" class="mail JSnocheck" title="&#x73;&#x75;&#x70;&#x70;&#x6f;&#x72;&#x74;&#x40;&#x62;&#x69;&#x74;&#x72;&#x65;&#x61;&#x63;&#x74;&#x69;&#x76;&#x65;&#x2e;&#x63;&#x6f;&#x6d;">&#x73;&#x75;&#x70;&#x70;&#x6f;&#x72;&#x74;&#x40;&#x62;&#x69;&#x74;&#x72;&#x65;&#x61;&#x63;&#x74;&#x69;&#x76;&#x65;&#x2e;&#x63;&#x6f;&#x6d;</a></div>
</li>
</ul>
<ul>
<li class="level1"><div class="li"> Try to re-install Java, and remember to use a full <acronym title="Java Development Kit">JDK</acronym>, <strong>not</strong> JRE.</div>
</li>
<li class="level1"><div class="li"> If you installed the 64-bit version of Eclipse, try the 32-bit version instead.</div>
</li>
<li class="level1"><div class="li"> If Eclipse is installed under C:\Program Files on <strong>Windows</strong> platform, install Eclipse in the user&#039;s home directory.</div>
</li>
</ul>

</div>
<!-- SECTION "3. Dependencies cannot be resolved problem" [817-] -->




<h1><a name="updating_the_reactive_blocks_sdk" id="updating_the_reactive_blocks_sdk">Updating the Reactive Blocks SDK</a></h1>
<div class="level1">

</div>
<!-- SECTION "Updating the Reactive Blocks SDK" [1-49] -->
<h2><a name="checking_for_updates_and_installation" id="checking_for_updates_and_installation">Checking for Updates and Installation</a></h2>
<div class="level2">

<p>

You can check for updates in two ways:
</p>
<ul>
<li class="level1"><div class="li"> Use <strong>Help / Check for Updates</strong>: This option checks for updates of <strong>all</strong> installed Eclipse features, and contacts <strong>all</strong> available update sites. This action is easy to invoke, but for some users this action takes a long time to complete.</div>
<ol>
<li class="level2"><div class="li"> In the main menu, select <strong>Help / Check for Updates</strong> </div>
</li>
<li class="level2"><div class="li"> The update manager checks the update sites for new features. This may take some minutes</div>
</li>
<li class="level2"><div class="li"> If an update is available, a dialog opens showing something like this:</div>
</li>
</ol>
</li>
</ul>
<ul>
<li class="level1"><div class="li"> Use <strong>Help / Install New Software</strong>: This is the same action as used to install new features, but can also be used for updating. Use this action if the first option takes a long time or does not complete.</div>
<ol>
<li class="level2"><div class="li"> In the main menu, select <strong>Help / Install New Software</strong></div>
</li>
<li class="level2"><div class="li"> Select the update site that you used to install the <acronym title="Software Development Kit">SDK</acronym></div>
</li>
</ol>
</li>
</ul>

<p>

In both cases, you will see the Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> listed in case there are updates:
</p>

<p>
<a href="/_detail/doc/available-updates.jpg?id=doc%3Aupdate_arctis" class="media" title="doc:available-updates.jpg"><img src="/_media/doc/available-updates.jpg" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> Select the features you want to update</div>
</li>
<li class="level1"><div class="li"> Select <strong>Next &gt;</strong> and follow the instructions</div>
</li>
<li class="level1"><div class="li"> Eclipse will ask if you want to restart:</div>
</li>
</ul>

<p>

<a href="/_detail/doc/restart.png?id=doc%3Aupdate_arctis" class="media" title="doc:restart.png"><img src="/_media/doc/restart.png" class="media" alt="" /></a>

</p>
<ul>
<li class="level1"><div class="li"> <strong>Restart.</strong> The Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> needs to reload all building blocks, which requires a restart.</div>
</li>
</ul>

</div>
<!-- SECTION "Checking for Updates and Installation" [50-1341] -->
<h2><a name="enabling_automatic_updates" id="enabling_automatic_updates">Enabling Automatic Updates</a></h2>
<div class="level2">

<p>
Eclipse has an option to check automatically for updates in the background, which you can enable in the preferences:
</p>

<p>
<a href="/_detail/doc/automatic-updates.jpg?id=doc%3Aupdate_arctis" class="media" title="doc:automatic-updates.jpg"><img src="/_media/doc/automatic-updates.jpg" class="media" alt="" /></a>
</p>

</div>
<!-- SECTION "Enabling Automatic Updates" [1342-1532] -->
<h2><a name="checking_the_current_version" id="checking_the_current_version">Checking the Current Version</a></h2>
<div class="level2">

<p>

Open the preferences and look which is the current version:
</p>

<p>
<a href="/_detail/doc/check-version.jpg?id=doc%3Aupdate_arctis" class="media" title="doc:check-version.jpg"><img src="/_media/doc/check-version.jpg" class="media" alt="" /></a>

</p>

</div>
<!-- SECTION "Checking the Current Version" [1533-] -->