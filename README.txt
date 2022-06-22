
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
	|				                    |
	|				                    |
	This part will assume that  |
	you meant for both peices 	|
	of data to be strings and 	|
	will put them together and 	|
	give you the result 1010	  |
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


-------------------------------------------------------------CSS--------------------------------------------------------------------------------------
css is used for the apperance of a web page

________________________________________________________________________________________________________________
#o { width: 600px; height: 400px; position: relative; margin-left:auto; margin-					|
right:auto;}													| 
.bubble { border: 2px solid #FFFFFF; display: block; position: absolute; border-radius: 20px; -webkit-border	| 
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

-------------------------------------------------------------------HTML--------------------------------------------------------------------------------

<h1> and </h1> (this of it as header 1) is called a tag 
and this tag means that whatever is inbetween themcis the largest and most important header on the page
	EX:<h1>I love bubbles!</h1>
		this will put "I love bubbles!" as the biggest and boldest thing on the webpage
<p> and </P> is like saying paragraph.




													


