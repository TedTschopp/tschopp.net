---
id: 160
title: 'A Little Calendar App I'm building'
date: 2006-04-07T17:57:34+00:00
author: Ted Tschopp
layout: post
guid: https://www.tedt.org/2006/04/07/a_little_calend/
permalink: /2006/04/07/a_little_calend/
categories:
  - Web
  - Coding
---
The following code is a calendar application I’m building in JavaScript. It needs a couple rounds of refactoring (to get rid of document.writes and to make it more object friendly).  The next step will be to make it handle iCal files (which will be a trick).  This is posted for all to enjoy. See the link at the end of this document.

&nbsp;

{% highlight html linenos %}<pre>&lt;style&gt;
  body {
   font-family: Verdana, Geneva, Arial, Helvetica, sans-serif;
  }
  .calendar{
   background-color: #F5F5F5;
  }
  
  .EndOfMonth {
   background-color: #ADD8E6;
   padding: 0 .1em 0 .1em;
  }
  .EndOfYear {
   background-color: Green;
   padding: 0 .1em 0 .1em;
  }
  .NotEndOfMonth {
   padding: 0 .1em 0 .1em;
  }
  .NotEndOfYear {
   padding: 0 .1em 0 .1em;
  }
  .today {
   background-color: #E6E6FA;
  }
  .weekend {
   color: Silver;
   font-size: .75em;
  }
  .calendarDate {
   width: 30px;
   padding: .25em 0em .25em 0em;
   margin: .25em 0em .25em 0em;
   text-align: center;
  }
  .calendarheader {
   width: 30px;
   padding: .25em 0em .25em 0em;
   margin: .25em 0em .25em 0em;
   text-align: center;
   background-color: Gray;
   color: White;
   font-weight: bold;
   text-transform: uppercase;
  }
  .calendarheader .weekend {
   width: 30px;
   padding: .25em 0em .25em 0em;
   margin: .25em 0em .25em 0em;
   text-align: center;
   background-color: silver;
   color: White;
   font-weight: bold;
   text-transform: lowercase;
  }
  .Notes {
   text-align: left;
   font-weight: normal;
  }
  .NotesMonth {
   background-color: #ADD8E6;
  }
  
 &lt;/style&gt;
&lt;script&gt;
 sunday = 0;
 monday = 1;
 tuesday = 2;
 wednesday = 3;
 thursday = 4;
 friday = 5;
 saturday = 6; 
 
 /* Convert to Date Properity */
 var Month = new Array();
 Month[0] = "Janurary";
 Month[1] = "Feburary";
 Month[2] = "March";
 Month[3] = "April";
 Month[4] = "May";
 Month[5] = "June";
 Month[6] = "July";
 Month[7] = "August";
 Month[8] = "September";
 Month[9] = "October";
 Month[10] = "November";
 Month[11] = "December";
 
 
 function startCalendar(date) {
  document.write('&lt;table class="calendar" cellpadding="0" cellspacing="0"&gt;&lt;tr class="calendarheader"&gt;');
  document.write('&lt;td class="Notes"&gt;Month&lt;/td&gt;');
  document.write('&lt;td class="NotEndOfYear"&gt;&lt;/td&gt;&lt;td class="NotEndOfMonth"&gt;&lt;/td&gt;');
  document.write('&lt;td class="weekend sunday weekend" id="sunday" title="Sunday" abbr="Sunday"&gt;s&lt;/td&gt;');
  document.write('&lt;td class="NotEndOfYear"&gt;&lt;/td&gt;&lt;td class="NotEndOfMonth"&gt;&lt;/td&gt;');
  document.write('&lt;td class="monday" id="monday" title="Monday" abbr="Monday"&gt;m&lt;/td&gt;');
  document.write('&lt;td class="NotEndOfYear"&gt;&lt;/td&gt;&lt;td class="NotEndOfMonth"&gt;&lt;/td&gt;');
  document.write('&lt;td class="tuesday" id="tuesday" title="Tuesday" abbr="Tuesday"&gt;t&lt;/td&gt;');
  document.write('&lt;td class="NotEndOfYear"&gt;&lt;/td&gt;&lt;td class="NotEndOfMonth"&gt;&lt;/td&gt;');
  document.write('&lt;td class="wednesday" id="wednesday" title="Wednesday" abbr="Wednesday"&gt;w&lt;/td&gt;');
  document.write('&lt;td class="NotEndOfYear"&gt;&lt;/td&gt;&lt;td class="NotEndOfMonth"&gt;&lt;/td&gt;');
  document.write('&lt;td class="thursday" id="thursday" title="Thursday" abbr="Thursday"&gt;&thorn;&lt;/td&gt;');
  document.write('&lt;td class="NotEndOfYear"&gt;&lt;/td&gt;&lt;td class="NotEndOfMonth"&gt;&lt;/td&gt;');
  document.write('&lt;td class="friday" id="friday" title="Friday" abbr="Friday"&gt;f&lt;/td&gt;');
  document.write('&lt;td class="NotEndOfYear"&gt;&lt;/td&gt;&lt;td class="NotEndOfMonth"&gt;&lt;/td&gt;');
  document.write('&lt;td class="weekend saturday weekend" title="Saturday" id="saturday" abbr="Saturday"&gt;s&lt;/td&gt;');
 } 
 function finishCalendar(date) {
  document.write('&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;');
 } 
 function output_calendar_day(date) {
  var outputclass = " calendarDate ";
  /* Output a day in a calendar */
  if(date.getDay()==sunday || date.getDay()==saturday ) {
   outputclass = outputclass + " weekend ";
  }
  if(date.getDay()==sunday) {
   outputclass = outputclass + " sunday ";
  }
  if(date.getDay()==monday) {
   outputclass = outputclass + " monday ";
  }
  if(date.getDay()==tuesday) {
   outputclass = outputclass + " tuesday ";
  }
  if(date.getDay()==wednesday) {
   outputclass = outputclass + " wednesday ";
  }
  if(date.getDay()==thursday) {
   outputclass = outputclass + " thursday ";
  }
  if(date.getDay()==friday) {
   outputclass = outputclass + " friday ";
  }
  if(date.getDay()==saturday) {
   outputclass = outputclass + " saturday ";
  }
  if (date.toDateString() == today.toDateString() ){
   outputclass = outputclass + " today ";
  }
  document.write('&lt;td title="' + date.toLocaleDateString() +'" class="'+outputclass+'"&gt;'+date.getDate()+"&lt;/td&gt;");
 }
 function output_end_of_week(date) {
  /* Handle the End of the week */
  document.write('&lt;/tr&gt;&lt;tr&gt;&lt;td class="Notes"&gt;&lt;/td&gt;');
 }
 function output_end_of_month(date) {
  /* Handle the output for the end of the Month */
  document.write('&lt;td class="EndOfMonth" id="'+date.getYear()+Month[date.getMonth()]+'" title="'+Month[date.getMonth()]+'"&gt;&lt;/td&gt;');
  var thisMonth=date.getYear()+Month[date.getMonth()];
  d=document.getElementById(thisMonth);
  d.parentNode.childNodes[0].innerHTML = Month[date.getMonth()];
  d.parentNode.childNodes[0].className = d.parentNode.childNodes[0] + " NotesMonth ";
 }
 function output_not_end_of_month(date) {
  /* Handle the output for the end of the Month */
  document.write('&lt;td class="NotEndOfMonth"&gt;&lt;/td&gt;');
 }
 function output_end_of_year(date) {
  /* Handle the output for the end of the Month */
  document.write('&lt;td class="EndOfYear" title="'+date.getYear()+'"&gt;&lt;/td&gt;');
 }
 function output_not_end_of_year(date) {
  /* Handle the output for the end of the Month */
  document.write('&lt;td class="NotEndOfYear"&gt;&lt;/td&gt;');
 }
 var oneDay = (60 * 60 * 24 * 1000)
 today = new Date();
 start = new Date();
 finish = new Date();
 DateOutput = new Date();
 DateOutputYesterday = new Date();
 start.setMonth(today.getMonth()-3);
 finish.setMonth(today.getMonth()+9);
 start.setDate(start.getDate() - start.getDay());
 startCalendar(start);
 for(i = start.valueOf(); i &lt; finish.valueOf(); i=i+oneDay) {
  DateOutput.setTime(i)
  DateOutputYesterday.setTime(i-oneDay);
  if (DateOutputYesterday.getDay()==6) {
   output_end_of_week(DateOutput);  
  }
  if (DateOutput.getYear() !== DateOutputYesterday.getYear()) {
   output_end_of_year(DateOutput);
  }else{
   output_not_end_of_year(DateOutput);
  }
  if (DateOutput.getMonth() !== DateOutputYesterday.getMonth()) {
   output_end_of_month(DateOutput);
  }else{
   output_not_end_of_month(DateOutput);
  }
  output_calendar_day(DateOutput);
 }
 finishCalendar(finish);
&lt;/script&gt;</pre>{% endhighlight %}

&nbsp;

<!--Creative Commons License-->

<a href="http://creativecommons.org/licenses/by-nc-sa/2.5/" rel="license"><img alt="Creative Commons License" border="0" /></a>
  
This work is licensed under a <a href="http://creativecommons.org/licenses/by-nc-sa/2.5/" rel="license">Creative Commons Attribution-NonCommercial-ShareAlike 2.5 License</a>.<!--/Creative Commons License--><!&#8211;

&#8211;>