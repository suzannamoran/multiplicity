//initiates variables and lists
var goalNumber;
var myNumber = 0;
var round = 10;
var score = 0;
var seconds;
var multipleNum;
var color;
var scoreList = [];
var initials;
var initialsList = [];

//sets screen to playScreen,setting all variables to their original values
onEvent("startButton","click",function(){
  if (getText("backgroundColor") == getText("buttonColor")) {
    setText("infoLabel","Please choose two different colors");
  }
  else{
  var length = getText("initialsInput");
  if (length.length > 6 || length.length < 1){
    setText("infoLabel","Please enter one to six characters");
  }
  else{
  setScreen("playScreen");
  score = 0;
  setText("scoreLabel","score: " + score);
  round = 10;
  multipleNum = randomNumber(1,11);
  goalNumber = multipleNum*randomNumber(0,10);
  myNumber = multipleNum;
  setText("myNumberLabel",myNumber);
  setText("goalNumberLabel",goalNumber);
  stopTimedLoop();
  timer();}
}});

onEvent("times0","click",function(){
  if(goalNumber/multipleNum == 0){
  updateScreen()}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times1","click",function(){
  if(goalNumber/multipleNum == 1){
  updateScreen();
  }
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times2","click",function(){
  if(goalNumber/multipleNum == 2){
  updateScreen()}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times3","click",function(){
  if(goalNumber/multipleNum == 3){
  updateScreen()}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times4","click",function(){
if(goalNumber/multipleNum == 4){  
  updateScreen()}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times5","click",function(){
  if(goalNumber/multipleNum == 5){
  updateScreen();}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times6","click",function(){
  if(goalNumber/multipleNum == 6){
  updateScreen();}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times7","click",function(){
  if(goalNumber/multipleNum == 7){
  updateScreen()}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times8","click",function(){
  if(goalNumber/multipleNum == 8){
  updateScreen()}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times9","click",function(){
  if(goalNumber/multipleNum == 9){
  updateScreen()}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
onEvent("times10","click",function(){
  if(goalNumber/multipleNum == 10){
  updateScreen()}
  else{playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3")}
});
  

//deducts 50 points from score,updates score and screen
onEvent("giveUpButton","click",function(){
  score = score - 200;
  playSound("sound://category_alerts/vibrant_game_negative_affirmation.mp3");
  setText("scoreLabel",score);
  multipleNum = randomNumber(1,11);
  myNumber = multipleNum;
  setText("myNumberLabel",multipleNum);
  goalNumber = multipleNum*randomNumber(1,10);
  setText("goalNumberLabel",goalNumber);
});

//returns user to startScreen and clears the initials textbox
onEvent("replayButton","click",function(){
  setScreen("startScreen");
  setText("initialsInput","");
});

//updates the user interface to reflect the correct score, myNumber, and goalNumber
//checks for successes and determines when to end the game
function updateScreen(){
  
  //when the user reaches the goal number, the round count decrease by 1, their score increases by 500 with 
  //5 points deducted for each second it took, and the goal number changes as the user's number returns to 0
    setText("correct",goalNumber/multipleNum);
    round = round - 1;
    score = score + 1000 - seconds*20;
    playSound("sound://category_achievements/lighthearted_bonus_objective_4.mp3");
    setTimeout(function() {
    setText("correct","");
    setText("scoreLabel",score);
    if (round > 0) {
      multipleNum = randomNumber(1,11);
      goalNumber = multipleNum*randomNumber(1,10);
      myNumber = multipleNum;
      setText("myNumberLabel",myNumber);
      setText("goalNumberLabel",goalNumber)}
}, 1000);

  //when round reaches 0, the game ends. The timer is stopped and the contents of the initialInput are stored in 
  //the variable 'initials'. The function highScore is called and the screen is set the leaderboardScreen
  setTimeout(function() {
  if (round == 0){
    stopTimedLoop;
    initials = getText("initialsInput").toUpperCase();
    highScore(score);
    setScreen("leaderboardScreen");
    
    //loops through defined initialsList indexes, making according number of score labels appear and displaying
    //the initials and scores that correlate to that index from initialsList and scoreList
  for(var i=0; i<5; i++){
    console.log("line143");
    if (scoreList[i] != undefined){
      console.log("line 145");
      showElement("highScore" + i);
      setText("highScore" + i,initialsList[i] + " : " + scoreList[i]);
     }}}}
, 1000)}

//sorts scores from high to low for the leaderboard
//parameter = score (number)
function highScore(score){
  //traverses scoreList, checking the value of the variable "score" (the user's current score) against scoreLists's
  //items (previous scores) to determine where in the list to place the new score (and corresponding initials in
  //initialsList)
  for(var i=0; i<(scoreList.length); i++){
    console.log("loop");
    //if new score is greater than a scoreList value, it is inserted at that index, moving all other items down.
    // i is then set to scoreList.length to break the loop so "score" is not inserted again.
    if(scoreList[i] < score){
      insertItem(scoreList,i,score);
      insertItem(initialsList,i,initials);
      i = scoreList.length + 1;
    }
    //if the new score is equal to a previous score, it is set to the index directly below so the initials of
    //the user who got the score first appear higher on the leaderboard.
    
    
    //test code for in order repeat scores
    //if(scoreList[i] == score){
     // console.log("line 168");
     // for (var count = i; count <= scoreList.length; count++) {
     //   console.log("loop running");
     //   if (scoreList[count] < score || scoreList[count] == undefined) {
      //    console.log("score added");
      //    insertItem(scoreList,count,score);
     //     insertItem(initialsList,count,initials);
     //     i = scoreList.length + 1;
     //   }
     //   }
    //}}
    
    if(scoreList[i] == score){
      insertItem(scoreList,i + 1,score);
      insertItem(initialsList,i + 1,initials);
      i = scoreList.length + 1;
    }}
    
    //if scoreList is empty OR the new score is lower than the lowest score in scoreList, it is added to the end
  if (scoreList.length === 0||scoreList[scoreList.length - 1] > score){
  appendItem(scoreList,score);
  appendItem(initialsList,initials);
}}

//timer increases variable 'seconds' by one each second and displays this on the playScreen. 'seconds' is
//also used to adjust the user's final score for time penalties.
function timer() {
  seconds = 0;
  timedLoop(1000, function() {
  seconds = seconds + 1;
  setText("timerLabel", seconds + " seconds");
 });
   }
  
onEvent("backgroundColor","change",function(){
  colors("backgroundColor");
  setProperty("playScreen","background-color",color);
  setProperty("leaderboardScreen","background-color",color);
  setProperty("backgroundColor","background-color",color);
 if (color != "#ffffff"){
   setProperty("instructionLabel","text-color","#ffffff");
   setProperty("timerLabel","text-color","#ffffff");
   setProperty("scoreLabel","text-color","#ffffff");
   setProperty("myNumberLabel","text-color","#ffffff");
   setProperty("label1","text-color","#ffffff");
   setProperty("correct","text-color","#ffffff");
   setProperty("label2","text-color","#ffffff");
   setProperty("goalNumberLabel","text-color","#ffffff");
   for(var count=0; count<5; count++){
  setProperty("highScore" + count,"text-color","white")}
 }
  });

onEvent("buttonColor","change",function(){
  colors("buttonColor");
  setProperty("startButton","background-color",color);
  setProperty("replayButton","background-color",color);
  setProperty("buttonColor","background-color",color);
  for(var i=0; i<11; i++){
  setProperty("times" + i,"background-color", color)}
  });

function colors(element){
  if (getText(element) == "Red") {
    color = "#ff0000"}
  if (getText(element) == "Blue") {
    color = "#0088ff"}
  if (getText(element) == "Green") {
    color = "#0fdc28"}
  if (getText(element) == "Orange") {
    color = "#ffb500"}
  if (getText(element) == "White") {
    color = "#ffffff"}
  if (getText(element) == "Black") {
    color = "#000000"}
}
