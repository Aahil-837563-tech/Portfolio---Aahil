# Third Reflection

5 day log entry:

Journal entry 1: Variables & Data Tracking
a) What concept did you implement? State the topic clearly and include a relevant code snippet.
On this day I implemented various different variables within my code to ensure easy to understand and transferable values that can be used in multiple parts of the code. Code snippet below ↴

“int nights, maxNights, fearMeter, fearSpeed, batteryMeter,batteryMeterMax, batterySpeed, batteryStart, oxygenMeter, oxygenSpeed, clockStart, clockStop, nightDuration, flashlightX, flashlightY;
boolean flashlightOn, hideUnderBlankie, startScreen, playGame;
String playHistory;
PImage titleScreen, mainGame, blanketOverlay, flashlightCircle, emptyBed, blanketBed, flashLight, batter100, battery75, batter50, battery25;”

b) Where did you use it, and why did you implement it that way? Explain the purpose of the code and your reasoning behind the approach you chose.
These variables will be used throughout the code and will constantly be updating whether they are boolean or integers. An example could be making a variable equal true after a certain condition so that another part of the code starts running. This particular way will most likely be used for starting the game, ending the game, and many more. I also ensured each variable has a self explanatory name to it so it’s easy for me to understand and explain the code.

c) What challenges did you encounter, and how did you fix them? Describe any issues you faced and the steps you took to resolve them.
I did not face many issues when creating variables because I had already planned a bunch during my planning phase, within the pseudocode. The only issue I can think of is not having enough variables or having irrelevant variables. This issue will automatically be solved as I continue the project as I will notice if I need more or less variables.


Journal Entry 2: Selection Structure
a) What concept did you implement? State the topic clearly and include a relevant code snippet.
On this day I implemented multiple selection methods like, if statements. This makes programs “smart" by allowing them to react to different situations and user inputs. Code snippet below ↴

“if (startScreen == true) {
    image(titleScreen, 0, 0, width, height);
    if (keyPressed) {
      if (key == ENTER) {
        startScreen = false;
        playGame = true;
        fill(0);
        rect(0, 0, width, height);
        image(mainGame, 0, 0, width, height);
        image(blanketBed, 0, 0, width, height);
      }
    }
  }”

b) Where did you use it, and why did you implement it that way? Explain the purpose of the code and your reasoning behind the approach you chose.
I use this in a lot of different methods because I want to make sure multiple things don't happen at once. For example I don't want the title screen to continue being displayed after the user presses the “Enter” key. I also tied it in with the first log entry, variables as my updateFashlight() method will only work if the variable playGame is true and if the flashlightOn variable is true, the flashlight mechanic will work. All these uses of selection ensure nothing collides visually or internally and makes sure everything functions as intended.

c) What challenges did you encounter, and how did you fix them? Describe any issues you faced and the steps you took to resolve them.
One challenge I encountered was struggling to get the flashlight to close after pressing the “F” key again after it had opened. I fixed this issue by dividing that code into the keyPressed() method and creating a toggle and using the NOT feature. ↴

“void keyPressed() {
  if (playGame == true) {
    if (key == 'f' || key == 'F') {
      flashlightOn = !flashlightOn;
    }
  }
}”


Journal Entry 3: Arrays & Data Structures
a) What concept did you implement? State the topic clearly and include a relevant code snippet.
On this day I implemented arrays to assign multiple values to the same variable. This makes variable management more efficient if it’s applicable so that you can do the same thing to different versions of a variable (will go into more detail in next question.) Code snippet below ↴

“float[] enemy1X = {2, 3};
float[] enemy1Y = {2, 3};
float[] enemy1Speed = {2, 3};
boolean[] enemy1Active = new boolean [2];”

b) Where did you use it, and why did you implement it that way? Explain the purpose of the code and your reasoning behind the approach you chose.
I have not used the arrays as of yet but I’m planning to use them for 1 monster. Because that monster can appear on the left side door or the right side door, I want to make the arrays have the initial locations at each, and then later on using a for loop to make them both move closer into the room, this makes it so that I have less code to rewrite for each monster and keeps the code more compact.

c) What challenges did you encounter, and how did you fix them? Describe any issues you faced and the steps you took to resolve them.
I have not encountered any challenge yet as I haven’t used the arrays yet, but a potential issue may be the movement of the monsters. If the left side monster moves diagonally to the right but the right side monster moves diagonally to the left, it might make it hard to use the same code for both, therefore making it potentially useless for the use of an array. I think one way to solve this would be to add an if statement that checks if the monster is the one from the left side or the one from the right side.


Journal Entry 4: Repetition Structure
a) What concept did you implement? State the topic clearly and include a relevant code snippet.
On this day I implemented repetition structures so that the same code runs each array value. This makes array management more efficient as well as reducing the lines of code used Code snippet below ↴

“for (int i = 0; i < 2; i++) {
    enemy1Active[i] = false;
  }”

b) Where did you use it, and why did you implement it that way? Explain the purpose of the code and your reasoning behind the approach you chose.
I have used repetition in multiple places, namely whenever it comes to enemy1 as it can spawn either from the left door or the right. Since it's the same enemy but with different starting initial values I used a for loop to go through both so that it works. In the code snippet above I put that is setup() and it makes both enemies 11’s inactive without having to re-write the same thing twice.

c) What challenges did you encounter, and how did you fix them? Describe any issues you faced and the steps you took to resolve them.
Some challenges that I encountered were 1 enemy not spawning in the right area but it was a quick fix as I used a rectangle to find a good initial value and replaced it with the x/y value for the specific array that was facing the issues. Some other issues were not putting code within the for loop so it wouldn't apply to any of the monsters.


Journal Entry 5: Use of Custom Functions & Error Checking/Restrictions
a) What concept did you implement? State the topic clearly and include a relevant code snippet.
On this day I implemented a couple of key methods, each having their own purpose and supporting the game. Within these methods I also added error checking/restrictions to ensure smooth gameplay. Code snippet below ↴

“void updateBattery() {
  if (flashlightOn == true) {
    batteryMeter -= 1;
  }
  if (playGame == true) {
    image(battery100, 0, 0, 322/3, 169/3);
    if (batteryMeter >= 956.25)
      image(battery100, 0, 0, 322/3, 169/3);
    else if (batteryMeter >= 637.5 )
      image(battery75, 0, 0, 322/3, 169/3);
    else if (batteryMeter >= 318.75)
      image(battery50, 0, 0, 322/3, 169/3);
    else if (batteryMeter > 0)
      image(battery25, 0, 0, 322/3, 169/3);
    else if (batteryMeter <= 0) {
      image(battery0, 0, 0, 322/3, 169/3);
      flashlightOn = false;
    }
  }
}”

b) Where did you use it, and why did you implement it that way? Explain the purpose of the code and your reasoning behind the approach you chose.
Almost all of my methods have restrictions so there’s no overlap in code causing any glitches. The code snippet above in particular is for the flashlight battery system, this includes the decrementing of the battery's meter as well as visual UI changes spending on the battery percentage. I make sure to only decrement the battery meter if the flashlight is on. In terms of the battery UI, I have 6 images each representing how much percentage the battery has left. This code ensures it displays the correct battery percentage at the correct time so that the player can keep track on how much battery they should save.

c) What challenges did you encounter, and how did you fix them? Describe any issues you faced and the steps you took to resolve them.
Some challenges that I encountered were that my battery meter max is too high. Initially I was unsure how long my games would be exactly and how much battery percentage would be adequate for a single night. I have decided to solve this issue by finishing the code for the whole game and then deciding how much battery the player should have to make it more engaging, rather than making it too easy or hard. I will most likely do this by dividing all the numbers put into the if, else if statements by the same number if the battery is too high or multiply if it’s too low.

