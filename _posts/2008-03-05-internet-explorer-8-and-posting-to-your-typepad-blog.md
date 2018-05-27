---
id: 458
title: Internet Explorer 8 and posting to your Typepad Blog
date: 2008-03-05T23:55:06+00:00
author:
  name: Ted Tschopp
  url: https://www.tedt.org/
  avatar: https://www.tedt.org/img/thumb3.jpg
layout: post

guid: https://www.tedt.org/2008/03/05/internet-explorer-8-and-posting-to-your-typepad-blog/
permalink: /2008/03/05/internet-explorer-8-and-posting-to-your-typepad-blog/
categories:
  - Programming
  - Web
  - Weblogs
---
I downloaded IE8 today and noticed it had a new way to post to Microsoft’s blog by highlighting some text and sending it off to their blogging service.

Here is the code that will make it work in Typepad:

<?xml version=&#8221;1.0&#8243; encoding=&#8221;utf-8&#8243; ?>
  
<openServiceDescription xmlns=&#8221;<http://www.microsoft.com/schemas/openservicedescription/1.0>&#8220;>
  
<homepageUrl>http://www.typepad.com/t/app</homepageUrl>
  
<display>
  
<name>Blog in Typepad</name>
  
<icon>http://www.tschopp.net/favicon.ico</icon>
  
<description>Post this in my Blog</description>
  
</display>
  
<activity category=&#8221;Blog&#8221;>
  
<activityAction context=&#8221;selection&#8221;>
  
<execute method=&#8221;get&#8221; action=&#8221;<http://www.typepad.com/t/app/weblog/post>&#8220;>
  
<parameter name=&#8221;title&#8221; value=&#8221;{documentTitle}&#8221; />
  
<parameter name=&#8221;SourceURL&#8221; value=&#8221;{documentUrl}&#8221; />
  
<parameter name=&#8221;blog_id&#8221; value=&#8221;16627&#8243; />
  
<parameter name=&#8221;text&#8221; value=&#8221;{selection}&#8221; />
  
<parameter name=&#8221;keywords&#8221; value=&#8221;{keywords}&#8221; />
  
</execute>
  
</activityAction>
  
<activityAction context=&#8221;document&#8221;>
  
<execute method=&#8221;get&#8221; action=&#8221;<http://www.typepad.com/t/app/weblog/post>&#8220;>
  
<parameter name=&#8221;title&#8221; value=&#8221;{documentTitle}&#8221; />
  
<parameter name=&#8221;blog_id&#8221; value=&#8221;16627&#8243; />
  
<parameter name=&#8221;SourceURL&#8221; value=&#8221;{documentUrl}&#8221; />
  
</execute>
  
</activityAction>
  
<activityAction context=&#8221;link&#8221;>
  
<execute method=&#8221;get&#8221; action=&#8221;<http://www.typepad.com/t/app/weblog/post>&#8220;>
  
<parameter name=&#8221;title&#8221; value=&#8221;{linkTitle}&#8221; />
  
<parameter name=&#8221;blog_id&#8221; value=&#8221;16627&#8243; />
  
<parameter name=&#8221;SourceURL&#8221; value=&#8221;{link}&#8221; />
  
</execute>
  
</activityAction>
  
</activity>
  
</openServiceDescription>

&nbsp;

  1. Copy and paste this into a Text file.
  2. Name it typepad.xml
  3. Replace blog_Id with your blog ID

  1. Browse to <http://www.typepad.com/t/app>
  2. Click on the blog you want to post to
  3. Observe the URL <http://www.typepad.com/t/app/weblog/manage?blog_id=16627>

&nbsp;

  * Replace the <icon> with your favicon
  * Save the document
  * Upload file to your Typepad account
  * Create a new HTML file
  * Name it typepad.html
  * Put the following code in the html file:<span style="font-family:monospace;"><A href=&#8221;javascript:window.external.addService(&#8216;http://www.tschopp.net/typepad.xml');&#8221;>Click Here</a></span>
  * Replace my URL with the URL to the XML file you created above
  * Save file
  * Upload File to Typepad
  * Browse to HTML file
  * Click on link

&nbsp;

My files are located at <http://www.tschopp.net/Typepad.html>

Let me know how it goes. I will post updates later this week to get more than just selections working. I also want to expand this to other services. Let me know how this is working for you.