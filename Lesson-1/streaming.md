---
layout: default
title: Streaming Services
description:   
---

###Identify which statements will be displayed when the following code is run. Be sure to place the statements in the order that the program will display them. 

```python
age = 14
subscription_type = "premium"
renewal_countdown = 10

if age > 16:
    print("You can watch R-rated movies!")

if age >= 13:
    print("PG-13 content is available!")

if age < 13:
    print("You may watch all content rated G or PG.")

if subscription_type == "premium":
    print("Premium users get 4K streaming!")

if subscription_type != "premium":
    print("Basic users stream in HD only.")

if renewal_countdown < 30:
    print("Your subscription will renew next month!")
```

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "PG-13 content is available!\n" +
    "You may watch all content rated G or PG.\n" +
    "Premium users get 4k streaming!\n" +
    "Your subscription will renew next month!\n" +
    "You can watch R-rated movies!#distractor\n" +
    "Basic users stream in HD only.#distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": false,
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
