---
id: 503
title: 'Script# Prototype from Nikhil Kothari'
date: 2006-05-23T17:28:39+00:00
author: Ted Tschopp
layout: post
guid: http://tedtschopp.wordpress.com/2006/05/23/script-prototype-from-nikhil-kothari/
permalink: /2006/05/23/script-prototype-from-nikhil-kothari/
categories:
  - Web
---
Script# brings the C# developer experience (programming and tooling) to Javascript/Ajax world. 

**How does it work?** 

Essentially the Script# compiler is a C# compiler that generates Javascript instead of IL. A key driving goal of the design is to produce readable Javascript that you may have authored yourself, and would be ok deploying into real apps. Hence the translation works at the C# level, as opposed to converting from IL to script, and the converter doesn't add any levels of abstraction itself.

There are a set of C# things that don't make sense (eg. lock, unsafe etc.) and set of things that are not supported yet (like generics). The converter does however provide support for key C# patterns such as foreach, delegates, and things like Debug conditionals. The associated class library (sscorlib, equivalent of mscorlib) is also tuned to Javascript. It doesn't contain the same stuff as mscorlib does. The approach taken is not to create a converter that converts an arbitrary existing application written in C#, and convert it to Javascript with something like a winforms abstraction layer. Instead, like Atlas, the idea behind Script# is oriented at providing an engineering approach and superior environment to developing applications using HTML/CSS and Javascript in a more productive, scalable and maintainable manner.

There is a small set of Javascript specific things (specifically closures and more functional style programming) that aren't supported in the conversion. There are equivalent alternatives, but feedback is needed. The implementation does allow you to hand-code some Javascript and expose it to the C# code in the form of assembly metadata. This provides a nice out for incorporating something that exists already, or something that needs more hand tuning.

For the full story [Click Here](http://www.nikhilk.net/Entry.aspx?id=121).

&#160;