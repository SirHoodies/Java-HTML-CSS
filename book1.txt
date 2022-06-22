
--------------------------------------JAVASCRIPT-------------------------------------------------------------------------------------------------------


NaN = not a number

alert(") will make a pop up with whatever is in the paranthisis 

a semicolon ";" seperates statements

for (var i=0; i<3000; i++) {document.write ("Idk");} --------- this writes "Idk" 300 times (for loop)

a backslash "\" escapes the quotation mark
	ex: for (var i=0; i<3000; i++) {document.write ("Joe said \"Hi\"");} prints out "Joe said "Hi"" 300 times

USE SPACING ITS EASIER TO READ

"{" groups peices of code which is called a block

"Shift + Enter" makes a new line without running the code

"//" makes a comment

"var" makes a variable
	variables cant have spaces
	".length" after a variable shows the length of the string
		everything in thee variable counts when you find the length (even the spaces)
	".indexOf()" shows the index number of the subject
		the index starts counting at 0 EX: "I like cheese".indexOf("I");
										0
"10"+10 will show 1010 but 10*"10" will show 100
	|				|
	|				|
	This part will assume that  	|
	you meant for both peices 	|
	of data to be strings and 	|
	will put them together and 	|
	give you the result 1010	|
					|
					This part will assume that you meant for the string "10" to actually be the number 10
					java does this because there is no way to multiply two strings together

Boolean data is either true or false
	EX: 1 < 10 //is 1 less than 10?
	Boolean(0) === Boolean(False)
	Boolean(1) === Boolean(True)
	True = 1
	False = 0

prompt("") gives a prompt (user input)
	you can assign a prompt to a variable like this:
		var username = prompt("What is your name?")
		console.log(username) //prints the variable username which is the prompt "What is your name"
		you can also type the variable "username" into the console and it gives you what you entered
		putting an "alert()" after printing a prompt will send an alert after the prompt
			var username = prompt("What is your name?")
			console.log(username)
			alert("Whack name")

"=" is called the assignment operator whic puts the value on the variable on the left

you can do different alerts like 
	alert("Hi") //prints hi
	alert(300) //prints 300
	alert(30*30) //gives you the product and puts it in the alert
	
	you can also add variables and the values of them into alerts
		var username1 = prompt("Whats your name"); //prompts you to ask what your name is then saves that answer as the value of "username1"
		var hscore = 30;

		alert("Hi, " +username1+ ". Your high score is: " +hscore); //the second plus after a string means you add something else
										(notice that there is no string after "+hscore")
Objects can store any data
	truck.color="yellow";
	truck.drive();

a web page is called a document so when you want to edit what a document says you use document.write() and anything you write will get writen onto the webpage
	document.write("Hello");
	document.write(12*12);

	Hello144

you can add a break with <br>

	document.write("Hello<br>");
	document.write(12*12);

	Hello 
	144

you can clear a webpage by typing chrome://newtab into the search bar


var toName = prompt("Enter your Name: "); //gives you a prompt to enter your name
    
var fromName = "The Grammy Awards"; //the value of "fromName" is "The Grammy Awards"

var letterBody = "We are please to inform you that your song,'Can\'t Stop Coding!,' has been voted the Best Song of All Time by the awarding committee.";

document.write("Dear " + toName + ",<br><br>");
document.write(letterBody + "<br><br>");
document.write("Sincerely,<br>");
document.write(fromName);


______________________________________________________________________________________________________________________________________________________
YUI().use('node', 'anim', 'anim-node-plugin', function(Y) {

    var o = Y.one('#o'),
        oW = o.get('offsetWidth'),
        oH = o.get('offsetHeight'),
        max = 36,						// this will change the maximum radius (size) of the circle
        min = 12,						// this will change the minimum size of the circle
        bubbles = 100,      // this controls how many bubbles will be spit out in total
        timerDelay = 8000;  // this controls the speed of which the bubbles are spit out

// so if you change bubbles = 10000 and timerDelay = 0, 10000 bubbles will comeout at once but if you do bubbles = 10 and timerDelay = 10000, 
10 bubbles will come out over 10 seconds

    function makeBubble() {
        var b = Y.Node.create('<span class="bubble"></span>');

        b.plug(Y.Plugin.NodeFX, {
            duration: 7,
            easing: Y.Easing.easeOut,
            to: {
                top: 0,
                opacity: 0
            },
            on: {
                end: function() {
                    Y.later(10000, this, function(){
                    animBubble(this.get('node'));
                    });
                }
            }
        });

        o.append(b);
        animBubble(b);
    }

    function animBubble(b) {
        var v = Math.floor(Math.random() * (max - min)) + min;

        b.setStyles({
            height: v + 'px',
            width: v + 'px',
            borderRadius: v + 'px',
            top: (oH + 2) + 'px',
            opacity: 1
        });

        b.setStyle('left', Math.floor(Math.random() * (oW - v)));

        b.fx.set('duration', Math.floor(Math.random() * 2 + 3));
        b.fx.set('to.top', Math.floor(Math.random() * (oH / 2)));


        b.fx.run();
    }

    for (i = 0; i < bubbles; i++) {
        Y.later(Math.random() * timerDelay, this, function() {
            makeBubble();
        });
    }

});
______________________________________________________________________________________________________________________________________________________

jsfiddle.net is where you can input java, html, and css all in one window

whenever something happens in a webpage it is called an event. (Clicking, Dragging, Dropping, hovering, selecting text, or pressing a key)
use .addEventListener to tell programs what to do when an avent happens

.addEventListener("click") // user clicks the mouse
.addEventListener("submit") // a form is being submitted
.addEventListener("drag") // an element is being dragged
.addEventListener("drop") // an element being dropped after being dragged
.addEventListener("copy") //the user has copied content
.addEventListener("paste") //the user has pasted content
.addEventListener("mouseover") //the mouse passed over an element
.addEventListener("load") //the page loads

EX: target.addEventListener("click", listener)

the element that java will listen for is called the event target

the listener is the third part of an .addEventListener statement is the actual listener. This is the object that should be notified when the event happens.
Normal format: target.addEventListener("event", listener);
EX: rightEye.addEventListener("click", moveUpDown);



_________MOVES ROBOT EYE UP AND DOWN WHEN PRESSED_______________

rightEye.addEventListener("click", moveUpDown);

var rightEye = document.getElementById("rightEye");
rightEye.addEventListener("click", moveupDown);

function moveUpDown(e) {
	var robotPart = e.target;	// this statement uses the event object (that comes automatically from the .addEventListener meathod) to find out what part of 
					the robot (what element) was clicked on. It stores the information about that element in a new variable called robotPart.
  var top = 0;				//this top variable is what well use to position the eye in each frame of the animation	
  
  var id = setInterval(frame, 10)	//the setInterval command will run the function listed first in the parenthisis and will do it on a schedule determined by the
  					number in the parentheses
function frame() {			// making a new function that will handle the task of creating each new animation frame
  	robotPart.style.top = top + '%';	//here we set the top value of top to the value of our top variable and add % at the end for the element that was
						clicked. so when you first click on the eye, top will be set to 0 percent, which will put it at the very top (head)
    top++;					//this line increases the value of top 1 using a thinf called the increment operator	
    if (top === 50){				// here we check if the final frame of animation was reached by seeing if top is equal to 50
    	clearInterval(id);			// the clearInterval statement ends the animation
    }
  }				//then clean up and close all of the brackets that we opened
}
_________________________________________________________________


-------------------------------------------------------------CSS--------------------------------------------------------------------------------------
css is used for the apperance of a web page

________________________________________________________________________________________________________________
#o { width: 600px; height: 400px; position: relative; margin-left:auto; margin-					|
right:auto;}													| 
.bubble { border: 2px solid #FFFFFFF; display: block; position: absolute; border-radius: 20px; -webkit-border	| 
-radius: 20px; -moz-border-radius: 20px; }									|
body {background-color:#2154B2;}										| 
________________________________________________________________________________________________________________| 
		
		^
		|
		|								  		
		This is the code used to make the bubble program. you can edit "border: 2px solid #FFFFFF"
		the "2px" changes the thickness of the bubbles and the "solid" changes the state of the bubble
			(you can use dotted, dashed, double, groove, ridge, inset, and outset)
		"#FFFFFF" is the color of the bubble border which is called hexadecimal notation
		It uses 3 set of 2 values (FF FF FF) which tels the browser how much red green and blue to put in
			(the range is from 00 to FF)
		"00" is Black and "FF" is white
		
_____________________________
body {				
    font-family: Arial;
}
_____________________________
these three lines for whats called a CSS rule which consist of two main components:
	Selector: The selector indicates what element or elements the CSS rule applies to. In the example, the selector is "body"
	
	Declaration block:The declaration block contains on or more CSS declarations, which indicate how to style the selected element or elements. In this example, we have just on declaration "front-family: Arial;" (this just changes the font of the text)
	
	
	
	
------------HTML-------------------
<div id="robot">
<div id="head">
    <div class="eye" id="righteye"></div>
    <div class="eye" id="lefteye"></div>
    <div id="nose"></div>
    <div id="mouth"></div>
</div>
<div class="arm" id="rightarm"></div>
<div id="body"><p>I &lt;3 JS!</p></div>
<div class="arm" id="leftarm"></div>
</div>


-------CSS---------
body {				//the first two are called element selectors. They select HTML elements using the name of the element
    font-family: Courier; 
}
p {
    font-size: 3em;
}
.eye {				//this is a class selector. it starts with a period meaning that it is selecting all of the elements that have class = "eye" 
    background-color:blue;	//you can also use a hexadecimal notation for the color (#8fc0e6) 
    width:20%;
    height:20%;
    border-radius: 50%;
}
.arm {
    background-color: #cacaca;
    position: absolute;
    top: 35%;
    width: 5%;
    height: 40%;
}

#head {				//ID selectors start with a hash symbol and select elements based on the value of the element's ID attribute. The robots have 
    width:30%;			different eye attributes (position). This is why both eyes are assigned the same class but different elements. the class allows
    height:30%;			you to change the eye color, width, radius, and height for both of them but the elements themselves have different positions
    border-radius: 15%;
    background-color: #dadada;
    position: absolute;
    left: 33%;
    top: 5%;
}
#righteye {			//CSS Declerations go inside decleration blocks following CSS selectors. Declerations are made up of two parts:
    position: absolute;			Property: The property of a decleration tells what should be modified. For example, you can change the color width of position 
    left: 20%;				of an element. The property must be followed by a colon(:)
    top: 20%;
}					Value: The value tells how the property should be changed
#lefteye {
    position: absolute;			each decleration must end in a semicolon(;)
    left: 60%;
    top: 20%;
}
#nose {
    position: absolute;
    left: 45%;
    top: 50%;
    width: 10%;
    height: 10%;
    background-color: black;
}
#mouth {
    position: absolute;
    width: 65%;
    height: 15%;
    left: 20%;
    top: 70%;
    background-color: red;
}
#body {
    position: absolute;
    left: 25%;
    top: 35%;
    width: 45%;
    height: 55%;
    background-color: #dadada;
    text-align:center;
    padding-top: 30px;
}

#rightarm {
    position:absolute;
    left:20%;
}
#leftarm {
    position: absolute;
    left: 70%;
}

hexadecimals: 0,1,2,3,4,5,6,7,8,9,a(10),b(11),c(12),d(13),e(14),f(15) |you can go to www.colorpicker.com|

CSS Property				JavaScript Style Property
-------------------------------------------------------------------
background-color			backgroundColor
border-radius				borderRadius
font-family				fontFamily
margin					margin
font-size				fontSize
border-width				borderWidth
text-aligncolor				textAligncolor
-------------------------------------------------------------------HTML--------------------------------------------------------------------------------

HTML stands for Hypertext Markup Language
HTML forms the skeleton that the text, pictures, and javascript in web pages to attach to

<h1> and </h1> (this of it as header 1) is called a tag 
and this tag means that whatever is inbetween themcis the largest and most important header on the page
	EX:<h1>I love bubbles!</h1>
		this will put "I love bubbles!" as the biggest and boldest thing on the webpage
<p> and </p> is like saying paragraph.

tags are made up of keywords inside of angle brackets "< and >"
tags are made up of two basic types: the begining tag "<p>" and the ending tag "</p>"

tags are easy to use, just put them before and after a body of text
	EX: <p>According to all known laws of aviation, there is no way a bee should be able to fly. Its wings are too small to get its fat little body off the ground. 	The bee, of course, flies anyway because bees don't care what humans think is impossible. Yellow, black. Yellow, black. Yellow, black. Yellow, black. Ooh, 	   black and yellow!</p> 
					(this is the begining of the bee movie)

HTML has more tags such as "<img>" for an image, "<audio>" for an audio, "<video>" for a video clip, "<header>" for the top of a webpage, and "<footer>" for the bottom of a web page.

______________________________________________________________________________
<html>
  <head>
    <title> My Grocery List</title>	//"<title>" is that displays at the top of the browser window ot in your browsers tab when youre on a webpage
  </head>
  <body>			// "<body>" just tells html that whatever is inside is the body
    <h1> Things I Need</h1>
      <ol>			// "<ol>" i makes an indent in the text (ol stands for ordered list)
        <li>Celery</li>   	// "<li>" makes a list with bullet points
        <li>Carrots</li>	// when you have a "<li>" inside of an "<ol>" it gives you an indented numbered list
        <li>Juice</li>
      </ol>
  </body>
</html>
_____________________________________________________________________________

These lines of code make a grocery list
The order of the tags must be in order of which they came (FILO which stands for First In, Last Out)
notice how the "<html>" is at the very beginings and the very end of the code
same with "<head>". its the second to first and the second to last tag in the code.

-------<html> ,<body> ,<head> should be in every web page------

_____________________________________________________________________________________
<html>
  <head>
    <title>HTML Template</title>
  </head>
  <body>
    <h1>
    this is h1
    </h1>
    <h2>
    this is h2
    </h2>
    <h3>
    this is h3
    </h3>
    <h4>
    this is h4
    </h4>
    <h5>
    this is h5
    </h5>
    <h6>
    this is h6
    </h6>
    <em>this is an emphasis</em> 	//"<em>" gives an emphasis onto text (italics)
  </body>
</html> 			//these are all the different sizes if headings (h1-6)
______________________________________________________________________________________

_______________________________________________________________________________________
<html>
  <head>
    <title>HTML Template</title>
  </head>
  <body>
    <h1>
    this is h1
    </h1>
    <h2>
    this is h2
    </h2>
    <h3>
    this is h3
    </h3>
    <h4>
    this is h4
    </h4>
    <div>
    this is a division
    </div>
    <h5>
    this is h5
    </h5>
    <h6>
    this is h6
    </h6>
    <em>this is an emphasis</em>
     <strong>this is strong</strong>
     <a>this is a link</a>
     <ul>
        <li>this is an unordered list (bulletpoints)</li>
     </ul>
     <hr>
  </body>
</html>
_____________________________________________________________________

<html>
  <head>
    <title>Fat boys only UwU</title>
  </head>
  <body>
    <h1 id ="myName">Jayden</h1>			//this is called an id attribute. Think of it as a variable but for HTML. You asign a value to the id. in this 
    <hr>						  in this case, that value is my name, Jayden. We can late edit this value with javascript.
    <p id="aboutMe"><em>Im a fat little boy</em></p>
    <hr>
    <h2>
    Things Fat little boys do
    </h2>
    <ul>
      <li id="firstThing">Eat</li>
      <li id="secondThing">Sleep</li>
      <li id="thirdThing">repeat</li>
    </ul>
  </body>
</html>
____________________________________________________________________

document.getElementById("id-value") 
this is how you fetch (select) an element in java
lets say you want to find your name in HTML with java script, write:
								document.getElementById("myName")

a property describes an aspect of an object. its something that an object has as opposed to something that an object does.

to change what an element says/ has inside, you use .innerHTML
lets say you have an element: 
				<p id="myParagraph">This is <em>my</em> paragraph.</p>        // this assigns an id value to "myParagraph" being the sentence inside

to change the value of its .innerHTML you would write this in java:
								   document.getElementById("myParagraph").innerHTML = "This is <em>your</em> paragraph.</p>";
								   	//this retrives the value of "myParagraph" and goes into the .innerHTML and you simply just
									type what you want it to have instead. You change the value of the element.
		
_____________________________HTML___________________________________________
<html>
  <head>
    <title>Fat boys only UwU</title>
  </head>
  <body>
    <h1 id ="myName">Jayden</h1>			
    <hr>						 
    <p id="aboutMe"><em>Im a fat little boy</em></p>
    <hr>
    <h2>
    Things Fat little boys do
    </h2>
    <ul>
      <li id="firstThing">Eat</li>    //makes the listed item have the id of "firstThing"
      <li id="secondThing">Sleep</li>
      <li id="thirdThing">repeat</li>
    </ul>
  </body>
</html>

<button id="changeList" type="button">    //makes a button with the id "changeList"
  Change Your List    			//gives the button a visible name
</button>
_______________________________________________________________________________
__________________________________JAVA_________________________________________
var item1;    //makes the variable item1
var item2;
var item3;

document.getElementById("changeList").onclick = newList; 
//changeList is the button and .onclick tells java to do something if you click the button (if statement kinda)
//if the button is pressed, run the function newList (which is defined below)

//we use a meathod called .getElementById to locate the element in the document that has an id attribute set to changeList (which is the value of the button). When java has found the button, we use the onclick event handler to tell it to watch for clicks on that button

function newList(){
item1 = prompt("Enter a new first thing: ");  //gives item1 a new thing to do (whis is to ask the prompt) and assigns it that value
item2 = prompt("Enter a new second thing: ");
item3 = prompt("Enter a new third thing: ");
updateList();          //once the user has answered all 3 prompts, it runs the funstion updateList
}

function updateList(){
document.getElementById("firstThing").innerHTML = item1;	//changes the .innerHTML of the original element
document.getElementById("secondThing").innerHTML = item2;
document.getElementById("thirdThing").innerHTML = item3;
}
//the update funtion finds each of the list items using their id attribute values. It then uses a meathod calles .innerHTML to change the value that is between the starting and ending tags of the list item to the values that the user entered by the user




	



