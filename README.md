# MC-Code-Gallery

Now that you learned how to create variables and if/else statements, it's time to apply it to creating your website.  But not just any website, an ICSpark project about Minecraft.  There are many possibilities of implementing Minecraft coding references to a website, but for the sake of this project, we'll just stick with an Entity Gallery and Overworld Layers. 

![Gallery1](images/Examples/MC_DataTypes_Gallery.png)
![Gallery3](images/Examples/Overworld_Layers_Gallery.png)

I'd like to give you a **warning** that this project could be lengthy.  Not to mention, this may be a long read as this read me file has around 300 lines of text.  Hence, why this project is divided into 5 parts. 

## Objectives

Use **JavaScript** to display text and manipulate elements on webpages.  Also, use HTML and CSS to display annd format images on webpages.
  1. Create a gallery of Entity data types
  2. Create a gallery of Game Rule data types
  3. Create another webpage that lets the user click on the arrow buttons to change the vertical position along with the Minecraft environment

## Prerequisites

To complete this project, students should have the following:
  + Basic understanding of HTML structures and attributes.
  + Basic understanding of CSS properties.
  + Basic understanding of JavaScript.
    + int, float, string, and bool variables
    + if/else statements

## Concepts

| HTML | Description |
| ------------- | ------------- |
| br | The line break element |
| img | Element that embeds an image on a webpage |
| pre | The preformatted text element |

The `<br>` tag is pretty handy when you want to format your webpage by creating vertical line spacing between text and images.  This would make your webpage look nicer instead of having every element compacted so close to each other.  
The `<pre>` tag is similar to the `<p>` tag, however, it preserves the whitespaces (" "), line breaks ("\n"), and other escape sequence characters from JavaScript code, unlike the paragraph element.  It's what makes outputting JavaScript code onto a webpage more effective.

More information about `<pre>` can be found at [W3Schools](https://www.w3schools.com/tags/tag_pre.asp) and [Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre). 

| JavaScript  | Description |
| ------------- | ------------- |
| \t | escape sequence for horizontal tab |
| string concactenation (+) | joins 2 or more strings together |
| string concactenation (+=) | joins 1 or more strings together into an existing string variable |

When you find coding several whitespaces to be tiring, use `\t` as it's equivalent to about 8 whitespaces.  It is somewhat similar to the horizontal version of a line break.

### String Concactenation

String Concactenation is the process of adding two strings together to form one string.  In other words, it's like joining two words together.  For example, appending "Poly" and "gon" gives us "Polygon".  Let's see how string concactenation works in JavaScript.

```js
// the whitespace helps us read the two words easily
console.log("Removed" + " " + "Herobrine");
```
Result: Remove Herobrine
```js
// string concactenation with variables
var string1 = "Glitch Art";
var string2 = " is so cool!";

console.log(string1 + string2);
// Result: Glitch Art is so cool!
```
Notice how there's a whitespace right before "is" in the variable string2.  This is a shorter way of doing ```console.log("Glitch Art" + " " + "is so cool!")```.  It may look aesthetically weird, but it makes your code more compact by typing less code.  In other words, it's the opposite of doing more work than you should.  Without the whitespace, the result would be "Glitch Artis so cool!", which makes the reader more confused whether "Artis" is another word or "Artis" is supposed to be "Art is".
```js
var game = "Minecraft is about ";
var genre1 = "building";
var genre2 = "exploring";
var genre3 = "adventuring";
var genre4 = "mini games.";

// string concactenation by appending multiple string variables into one string variable
game += genre1 + ", " + genre2 + ", " + genre3 + ", and " + genre4;

console.log(game);
// Result: Minecraft is about building, exploring, adventuring, and mini games.
```
Notice how '+=' is used to join multiple strings together.  This is to add more information to the same string variable.  It'll come in handy when you don't want to type a long-baked horizontal line of code.  If you want to add more strings to a string variable, you can press enter and type the same thing again but with different string variables. 

## Your Challenge

### Part I: Setup

Make sure to have the following files:
  + index.html
  + overworld_layers.html
  + style.css
  
Create the following files:
  + variables.js
  + script.js

### Part 2A: 1st HTML File (index.html)

  1. create an ```<a>``` tag that displays "Overworld Layers"
      + its <a> tag should link to overworld_layers.html
      
Completing Part2A means you have 4 images and two pre tags.  Feel free to use <br> tags to properly format your webpage.

### Part 2B: 2nd HTML File (overworld_layers.html)

  1. create an ```<a>``` tag that displays "MC Data Types"
      + its <a> tag should link to index.html

### Part 3A: 1st JavaScript File (variables.js) 

  1. link variables.js to index.html at the end of the ```<body>``` tag:
  2. create the following string variables
      + dataType, stores "bool "
      + variableName1, stores "activateGlitchArt"
      + variableName2, stores "keepInventory"
  3. create the following boolean variables
      + boolValue1, stores false
      + boolValue2, stores true
  4. apply the following code snippet (mentors, please make sure the students have this code snippet)
  ```js
  // gets the element id called booleans1
  var paragraph1 = document.getElementById("booleans1");

  // gets the element id called booleans2
  var paragraph2 = document.getElementById("booleans2");
  ```
  5. Use ```.innerHTML``` and string concactenation to display text to the webpage
  
  Here's the first part of the answer of step 5:
  ```js
  // adds multiple variables in a row to form 2 defined boolean variables
  paragraph1.innerHTML = dataType + variableName1 + " = " + boolValue1;
  paragraph1.innerHTML += "\t\t\t\t" + dataType + variableName1 + " = " + boolValue2;
  ```
  Please incllude this code snippet and do the same for the variable paragraph2.

### Part 3B: 2nd JavaScript File (script.js)

  1. link script.js to overworld_layers.html at the end of the ```<body>``` tag:
  2. add the following code snippet:
  ```js
  // used to change the image
  var layer = document.getElementById("imageLayer");

  // used to decrease the displayed y_position value
  var descendVeritcally = document.getElementById("descend");
  // used to increase the displayed y_position value
  var ascendVeritcally = document.getElementById("ascend");

  // used to display the y_postion on the webpage
  var verticalPosition = document.getElementById("getVerticalPosition");

  // used to get the name of the layer depending on the y_position
  var location_name = document.getElementById("layerName");
  ```
  
  (Mentors, have students copy and paste the above code snippet to their script.js file)
  
  3. create a variable called y_position that stores an int value of 5
  4. add the following code snippets
  ```js
  // have the left arrow "button" manipulate the webpage when clicked on
  descendVertically.addEventListener("click", function() {
    // continue coding steps 5 through 8 in here
  });
  
  // have the right arrow "button" manipulate the webpage when clicked on
  ascendVertically.addEventListener("click", function() {
    // continue coding steps 5 through 8 in here
  });
  ```
  
 (Mentors, have students copy and paste the above code snippet to their script.js file)
  
  5. decrement the y_position by 1 inside the unnamed function of descendVertically
  6. increment the y_position by 1 inside the unnamed function of ascendVertically
  7. Update the y_position on the webpage by using ```.innerHTML``` to verticalPosition.  
  8. Create an if/else statement.  The if/else statement should inculde: 
      + if y_position is greater than or equal to 20
        + layer.src would be Sky.jpg
        + location_name.innerHTML would be "Layer: Above the Clouds"
      + else if y_position is greater than or equal to 10
        + layer.src would be mountains.webp
        + location_name.innerHTML would be "Layer: Mountains"
      + else if y_position is greater than or equal to 5
        + layer.src would be plains.jpg
        + location_name.innerHTML would be "Layer: Plains"
      + else if y_position is greater than or equal to 2
        + layer.src would be Cave.webp
        + location_name.innerHTML would be "Layer: Caves"
      + else if y_position is greater than or equal to 0
        + layer.src would be Lava_Cave.webp
        + location_name.innerHTML would be "Layer: Lava Caves"
      + else
        + layer.src would be The_Void.webp
        + location_name.innerHTML would be "Layer: Void"
        
layer.src represents the image source, which is used to change the image.  location_name.innerHTML is used to change the text on the webpage.  Remember to use the proper file paths for your images.  

## Stretch Goals

### Add more to overworld_layers.html

Add more else if's to your if/else statement and use images such as DeepDark.webp, Deepslate_Cave.webp, Forest.webp, Jungle.webp, and Space.png 

### Add CSS to your website

| CSS  | Description |
| ------------- | ------------- |
| @import url | imports other stylesheets, including custom fonts, into an existing CSS file |

We'll use `@import url("#");` to import a custom font into this project.  The "#" represents a website link to a custom font.  Like any programming language, `@import url("#");` must be used at the very top of your CSS file.

Side note: URL stands for uniform resource locator

  1. create a CSS file called style.css  
  2. link your CSS file to both of your HTML files by doing the following in the ```<head>``` tag:
  ```html
  <!-- enables the CSS file to format and decorate the webpage -->
  <link rel="stylesheet" href="style.css">
  ```
  3. import the minecrafttia font by typing in the following:
  ```css
  /* minecraft font is ready to be used */
  @import url("https://fontlibrary.org//face/minecraftia");
  ```
This will only make the minecraftia font available to use for your webpage. So, to change the default font to the minecraftia one, you must also change the font-family attribute for certain CSS selectors.    
  4. give the following attributes to the body selector
        + backgroud image is dirt_background.jpg
        + font-family is MinecraftiaRegular
  5. give the following attributes to the h1 selector
        + color is white
        + text align is center
  6. give the following attributes to h2 and h3 selectors
        + color is white
        + **Hint:** you can either create 2 separate selectors or merge them into one selector
  
  CSS template of 2 selectors in 1:
  ```css
  selector1, selector2 {
    attribute: value;
  }
  ```
  7. give the following attributes to the pre selector
      + color is white
      + font family is MinecraftiaRegular
      + font size is larger
    
The reason why we update the font family to the pre tags is because the font from console.log() cannot be changed.  So, we must change the JavaScript text via the pre selector.
  
  8. create a class selector called centerElements, and the the following attributes should have:
      + display is block
      + text align is center
      + margin left is auto
      + margin right is auto
  9. create an 'a' selector and give the following attributes:
      + text align is center
      + color is rgb(0, 255, 0)
      + background color is gray
      + font size is 21px
      + text decoration is none (no underline for links)

Don't forget to add divs in your HTML files

### Make hover animations for links

You learned how to color the text of the link, give it a background color, and change its font size.  You also learned how to position the link.
```css
a {
    color: rgb(0, 255, 0);
    background-color: gray;
    font-size: 21px;
    text-align: center;
    text-decoration: none;
}
```
Now try making the link's text color white and have it change to orange if the mouse cursor is hovering over it.

### Create an input box instead of arrow "buttons"

The advantage of having arrow "buttons" is having more user interaction.  The disadvantage is it can take a lot of time to go through a large range of numbers(unless if your variable can increment/decrement by a large amount).  A way around this disadvantage is by making the y_position range smaller.  But in Minecraft, going deep underground takes more than a few blocks.  So, an input box lets you type in a number and display the result in seconds.  You could create a ```<form>``` tag but that would redirect to a webpage.  Instead of going through that hassle, you can create an input tag and a button tag.  
Although it's easy to implement an input box, you'll deal with more test cases.  Like most programming languages, input returns a string value.  Because of this, you must check if the input contains letters or other non-numeric characters.  If it is, then display an error message.  Otherwise, convert the input value into a number.  In order to compare your input value with numbers, it must be converted to a number.          

### Create another webpage of Minecraft coding references

Apply conditional operators (<, >, <=, >=, ==, !=) to ranking minecraft armor.  Apply the &&(and) and the ||(or) logical operators to when the player is able to go to sleep.  Those conditions are when it's night time or there's a thunderstorm and when there's no hostile mobs nearby.  Apply the !(not; negation) logical operator to when the mob is not hostile, the iron golem and snow golem won't attack that mob.  No if/else statements are invovled, however, try to output text to the webpage via a JavaScript file.  You can also apply int, float, and string variables to the rest of the minecraft images provided in the images zip file.  Not to mention, try to include "\n" to your JS files.   
