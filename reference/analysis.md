
---
title: Analysis
layout: reference
---

<h1><a name="analysis" id="analysis">Analysis</a></h1>
<div class="level1">

<p>
The Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> includes a built-in automatic verification tool that reveals some mistakes and design flaws and provides possible actions to fix them. To start the analyzing, select <em>“Analyze”</em> from the context menu or the analysis icon (<a href="/_detail/doc/analysis-button.jpg?id=doc%3Aanalysis" class="media" title="doc:analysis-button.jpg"><img src="/_media/doc/analysis-button.jpg" class="media" alt="" /></a>) at the top right part of the Behavior page. 
</p>

<p>

<a href="/_detail/doc/start-analysis.jpg?id=doc%3Aanalysis" class="media" title="doc:start-analysis.jpg"><img src="/_media/doc/start-analysis.jpg" class="media" alt="" /></a>
</p>

<p>

You can also analyze all building blocks within a project by selecting <em>“Analyze Project”</em> from the context menu of the project.
</p>

</div>
<!-- SECTION "Analysis" [1-515] -->
<h2><a name="analysis_result" id="analysis_result">Analysis Result</a></h2>
<div class="level2">

<p>
An example of an analysis result is depicted in the following figure.
</p>

<p>
<a href="/_detail/doc/analysis-result3.jpg?id=doc%3Aanalysis" class="media" title="doc:analysis-result3.jpg"><img src="/_media/doc/analysis-result3.jpg" class="media" alt="" /></a>
</p>

<p>
The result is shown in the Analysis view <strong>(1)</strong>. If the view is not open, choose it from the bottom tool bar.
There are two kinds of issue:
</p>
<ul>
<li class="level1"><div class="li"> Errors (<a href="/_detail/doc/error_tsk.gif?id=doc%3Aanalysis" class="media" title="doc:error_tsk.gif"><img src="/_media/doc/error_tsk.gif" class="media" alt="" /></a>) are problems that <strong><em class="u">must be</em></strong> fixed. Usually, errors mean that a further analysis or implementation will not complete correctly.</div>
</li>
<li class="level1"><div class="li"> Warnings (<a href="/_detail/doc/warning.jpg?id=doc%3Aanalysis" class="media" title="doc:warning.jpg"><img src="/_media/doc/warning.jpg" class="media" alt="" /></a>) are situations that you should be <strong><em class="u">aware</em></strong> of since they can be signs of behavior that you did not intend.</div>
</li>
</ul>

<p>

Clicking each error <strong>(2)</strong> or warning will show an explanation on the problem <strong>(3)</strong> and some possible actions, if any, that you can take to fix it <strong>(4)</strong>.
</p>

</div>
<!-- SECTION "Analysis Result" [516-1269] -->
<h2><a name="two-step_analysis" id="two-step_analysis">Two-Step Analysis</a></h2>
<div class="level2">

<p>

The analysis internally runs in two steps, an initial syntactical inspection and a subsequent deeper analysis. Some syntactical errors prevent the deep analysis to run. Therefore, it may happen that fixing an error reveals other issues, once you analyze again. The opposite, fixing an issue also removes other issues, is also possible.

</p>

</div>
<!-- SECTION "Two-Step Analysis" [1270-] -->




<h1><a name="gallery_of_issues" id="gallery_of_issues">Gallery of Issues</a></h1>
<div class="level1">

<p>

The Reactive Blocks <acronym title="Software Development Kit">SDK</acronym> generates executable code automatically from building blocks. In order to ensure correct implementation, it is important that all building blocks are consistent. For this purpose, the <acronym title="Software Development Kit">SDK</acronym> is equipped with <a href="/doc/analysis" class="wikilink1" title="doc:analysis">analyzer</a> and <a href="/doc/animation" class="wikilink1" title="doc:animation">animator</a> tools.
</p>

<p>
In the following we summarized what types of errors and warnings that are detected by the <acronym title="Software Development Kit">SDK</acronym>. 
For more information, just follow the links.
</p>

<p>



<style type="text/css">

table.levels td {
    background: #F0F4FA;
    padding: 5px;
}

td.levelsseparator {
    background: white;
    padding: 5px;
}

td.levelstitle {
    color: #6A90CB;
    font-size:1.5em;
    border-top: solid 1px #6A90CB;
    background: #F0F4FA;
}

td.levelscomment {
position:relative;
background: #DCE5F4;
}


/*CSS to show large image*/
.thumbnail{
  position: relative;
  z-index: 0;
}

.thumbnail:hover{
  background-color: transparent;
  z-index: 50;
}

.thumbnail span{ /*CSS for enlarged image*/
  position: absolute;
  background-color: #F0F4FA;
  border: 1px dashed #6A90CB;
  visibility: hidden;
}

.thumbnail span img{ /*CSS for enlarged image*/
  border-width: 0;
  padding: 2px;
}

.thumbnail:hover span{ /*CSS for enlarged image on hover*/
  visibility: visible;
  left: 30px; /*position where enlarged image should offset horizontally */
  top: -130px;
}


</style>


<table class="levels" style="border-collapse:collapse;">

<tr><td colspan="4" class="levelstitle">Inconsistent Graph</td></tr>

<tr><td colspan="4" style="levelscomment">Activity diagram contains inconsistent construction.</td></tr>

<tr>
<td>
<ul style="width:300px">
<li><a href="http://reference.bitreactive.com/issues/yc1">Cycle in activity diagram</a></li></ul><a class="thumbnail" href="http://reference.bitreactive.com/issues/yc1"><center><img src="http://reference.bitreactive.com/_media/issues/yc1s.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/yc1-error3.jpg"/></span></a>
</td>

<td>
<ul style="width:300px">
<li><a href="http://reference.bitreactive.com/issues/yc2">Illegal merge of concurrent flows</a></li></ul><a class="thumbnail" href="http://reference.bitreactive.com/issues/yc2"><center><img src="http://reference.bitreactive.com/_media/issues/yc2s.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/yc2-error4.jpg"/></span></a>
</td>

</tr>


<tr><td colspan="4" class="levelseparator" style="background: white;">&nbsp;</td></tr>
<!----------------------------------------------->

<tr><td colspan="4" class="levelstitle">ESM - related</td></tr>

<tr><td colspan="4" style="levelscomment">Issues related to ESM.</td></tr>

<tr>
<td>
<ul style="width:300px">
<li><a href="http://reference.bitreactive.com/issues/ae1">Flow(s) harm inner block's ESM</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/ae1"><center><img src="http://reference.bitreactive.com/_media/issues/ae1.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/ae1-ex1-error.jpg"/></span></a>
</td>

<td>
<ul style="width:300px">
<li><a href="http://reference.bitreactive.com/issues/ae2">Token(s) stopped from entering inner block</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/ae2"><center><img src="http://reference.bitreactive.com/_media/issues/ae2s.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/ae2.jpg"/></span></a>
</td>

</tr>

<tr>

<td>
<ul style="width:300px">
<li><a href="http://reference.bitreactive.com/issues/aa1">Flow(s) harm enclosing ESM</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/aa1"><center><img src="http://reference.bitreactive.com/_media/issues/aa1.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/aa1-error3.jpg"/></span></a>
</td>

<td>
<ul style="width:300px">
<li><a href="http://reference.bitreactive.com/issues/aa2">Token(s) stopped from leaving enclosing block</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/aa2"><center><img src="http://reference.bitreactive.com/_media/issues/aa2.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/aa2-warning.jpg"/></span></a>
</td>
</tr>

<tr>

<tr><td colspan="4" class="levelseparator" style="background: white;">&nbsp;</td></tr>
<!----------------------------------------------->
<tr><td colspan="4" class="levelstitle">Block Termination - related</td></tr>

<tr><td colspan="4" style="levelscomment">Issues related to termination of a block.</td></tr>

<tr>

<td>
<ul style="width:300px">
<li><a href="http://reference.bitreactive.com/issues/at2">Termination harms inner block</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/at2"><center><img src="http://reference.bitreactive.com/_media/issues/at2.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/at2-error3.jpg"/></span></a>
</td>

<td>
<ul style="width:300px">
<li><a class="thumbnail" href="http://reference.bitreactive.com/issues/at1">Termination leaves token(s) in join</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/at1"><center><img src="http://reference.bitreactive.com/_media/issues/at1s.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/at1-warning2.jpg"/></span></a>
</td>

</tr>

<tr>

<td>
<ul style="width:300px">
<li><a class="thumbnail" href="http://reference.bitreactive.com/issues/at3">Termination leaves token(s) in implicit join</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/at3"><center><img src="http://reference.bitreactive.com/_media/issues/at3.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/at3-warning.jpg"/></span></a>
</td>
<td/>

</tr>

<tr>

<tr><td colspan="4" class="levelseparator" style="background: white;">&nbsp;</td></tr>
<!----------------------------------------------->
<tr><td colspan="4" class="levelstitle">Others</td></tr>

<tr><td colspan="4" style="levelscomment">Others.</td></tr>

<tr>
<td>
<ul style="width:300px">
<li><a class="thumbnail" href="http://reference.bitreactive.com/issues/sp1">Several steps triggered by identical signal</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/sp1"><center><img src="http://reference.bitreactive.com/_media/issues/sp1.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/sp1-error.jpg"/></span></a>
</td>

<td>
<ul style="width:300px">
<li><a class="thumbnail" href="http://reference.bitreactive.com/issues/st2">Deadlock in block</li></ul></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/st2"><center><img src="http://reference.bitreactive.com/_media/issues/st2.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/st2-warning1.jpg"/></span></a>
</td>

</tr>

<tr>

<td>
<ul style="width:300px">
<li><a class="thumbnail" href="http://reference.bitreactive.com/issues/st1">Deadlock in system</li></ul></a></a><a class="thumbnail" href="http://reference.bitreactive.com/issues/st1"><center><img src="http://reference.bitreactive.com/_media/issues/st1.jpg"/></center><span><img src="http://reference.bitreactive.com/_media/issues/st1-warning.jpg"/></span></a>
</td>
<td/>

</tr>

<tr>

<tr><td colspan="4" class="levelseparator" style="background: white;">&nbsp;</td></tr>
<!----------------------------------------------->


</table>


</p>

</div>
