---
layout: default
title: Battery Level
description: Create a program that will prompt the user to enable low power mode if the battery level is 20% or less. Otherwise, the program should display an approximate number of hours left in the battery. 
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
  var initial = "battery_level = int(input(&quot;Enter battery level: &quot;))\n" +
    "if battery_level &lt;= 20:\n" +
    "    print(&quot;Low power mode?&quot;)\n" +
    "if battery_level &gt; 20:\n" +
    "    hours_remaining = battery_level / 10\n" +
    "    print(f&quot;Approximately {hours_remaining} hours of battery life remain.&quot;)";
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
