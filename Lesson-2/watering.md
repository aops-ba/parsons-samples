---
layout: default
title: Rainy Days
description: Rearrange the blocks to create a program that will inform the user whether or not they need to water their garden based on how many days since it has rained. The user should be told to water their garden for 5 minutes per day it has rained if it has been more than 2 days since rain.
---

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "days_since_rain = int(input(&quot;How many days since it rained? &quot;))\n" +
    "if days_since_rain &lt;= 2:\n" +
    "    print(&quot;The soil is still moist.&quot;)\n" +
    "else:\n" +
    "    water_minutes = days_since_rain * 5\n" +
    "    print(f&quot;Water your garden for {water_minutes} minutes.&quot;)\n" +
    "else days_since_rain &gt; 2:#distractor\n" +
    "if days_since_rain =&gt; 2:#distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
