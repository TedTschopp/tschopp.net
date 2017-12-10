---
id: 523
title: Reserved Worlds in XHTML for IE only
date: 2005-08-29T17:22:45+00:00
author: Ted Tschopp
layout: post
guid: https://www.tedt.org/2005/08/29/reserved-worlds-in-xhtml-for-ie-only/
permalink: /2005/08/29/reserved-worlds-in-xhtml-for-ie-only/
categories:
  - Weblogs
---
[Here](http://meyerweb.com/eric/thoughts/2005/08/26/when-printing-kills/) is an interesting article about the fact that the word "tag" is a reserved world in Internet Explorer for classes. Interesting. 

> Here’s a fascinating little tidbit: on some users’ machines, attempts to print out <a href="http://joeclark.org/" rel="acquaintance met">Joe Clark</a>’s [ALA](http://alistapart.com/) article “[Facts and Opinions About PDF Accessibility](http://alistapart.com/articles/pdf_accessibility)” would crash Internet Explorer. The error message mentioned a script error in line 1401: “Object doesn’t support this property or method”. Funny thing: we weren’t doing any scripting. The error was actually occurring `shdoclc.dll/preview.dlg`, which is of course a piece of the operating system.
> 
> <a href="http://jasonsantamaria.com/" rel="co-worker acquaintance colleague met">Jason</a> did some sleuthing and traced the crash to this line of markup:
> 
> <pre>&lt;h2 id="tags"&gt;Tags and structure&lt;/h2&gt;</pre>
> 
> Honestly, that was it. So <a href="http://zeldman.com/" rel="frind colleague met">Jeffrey</a> renamed the ID to read:
> 
> <pre>&lt;h2 id="structure"&gt;Tags and structure&lt;/h2&gt;</pre>
> 
> So far as we know, no more crashing in Explorer.
> 
> Ain’t browsers a _slice_?
> 
> (And yes, we’re aware of the clamor for a print style sheet. More on this later.)
> 
> **Update:** Marten Veldthuis from [Strongpsace](http://strongspace.com/) points out that [37signals](http://37signals.com/) ran into a very similar problem in [Backpack](http://www.backpackit.com/). Details can be found in [Jamis Buck](http://jamis.jamisbuck.org/)’s June 3rd post [ie-is-teh-3v1l](http://jamis.jamisbuck.org/articles/2005/06/03/ie-is-teh-3v1l). **Spread the word:** “tags” is effectively a reserved keyword, even though no such concept exists in (X)HTML. Use it at your (users’) peril.
> 
> > 
stin