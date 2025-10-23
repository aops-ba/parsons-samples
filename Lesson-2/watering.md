---
layout: default
title: Rainy Days
description: A garden needs 5 minutes of watering for each day since it last rained. It is recommended to wait at least 2 days after rain before watering. Rearrange the blocks to create a program that will give the correct recommendation based on the days since it last rained.
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
  var initial = "days_since_rain = int(input(&quot;Enter days since last rain: &quot;))\n" +
    "if days_since_rain &lt;= 2:\n" +
    "    print(&quot;Watering not recommended.&quot;)\n" +
    "else:\n" +
    "    water_minutes = days_since_rain * 5\n" +
    "    print(f&quot;{water_minutes} minutes of watering recommended.&quot;)\n" +
    "if days_since_rain =&gt; 2:#distractor\n" +
    "else days_since_rain &gt; 2:#distractor";
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
