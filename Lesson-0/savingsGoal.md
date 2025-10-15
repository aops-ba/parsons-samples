<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "current_balance = 150 - 32 - 3 + 46\n" +
    "savings_goal = 175\n" +
    "message = &quot;Keep saving!&quot;\n" +
    "if current_balance == savings_goal:\n" +
    "    message = &quot;You have reached your goal!&quot;\n" +
    "print(message)\n" +
    "current_balance == 150 - 32 - 3 + 46#distractor\n" +
    "savings_goal == 175#distractor\n" +
    "if current_balance = savings_goal:#distractor\n" +
    "message == &quot;You have reached your goal!&quot;#distractor\n" +
    "message == &quot;Keep saving!&quot;#distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.VariableCheckGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "sortableTrash",
    "vartests": [
        {
            "message": "Testing",
            "initcode": "",
            "code": "",
            "variables": {
                "current_balance": 161,
                "savings_goal": 175,
                "message": "Keep saving!"
            }
        }
    ]
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
