# JQuery 
## Introduction
   JQuery is a lightweight JS library provides features like
      - HTML/DOM manipulation
      - CSS manipulation
      - HTML event handle
      - Effects and animations
      - AJAX
      - Utilities
## Use JQuery by download and include it in your file or use CDN
   Here is Google CDN: https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js
## Basic Syntax: $(selector).action()
   EX: document ready Event:
  ```
  $(document).ready(function(){
  });

  $(function() {
  });
  ```
## Selectors: JQuery uses CSS Selectors to target elements.
  JQuery Selectors Reference:
  https://www.w3schools.com/jquery/jquery_ref_selectors.asp
  - By Type: $("button"), $(document)
  - By Class: $(".classname")
  - By ID: $("#IDname")
  - By className:nth-child(n): $(".className:nth-child(3)")
  - By target based on positions using :odd or :even, $(".className:odd")

## JQuery Syntax For Event
   Some common DOM events:
   Mouse Events | Keyboard Events | Form Events | Document/Window Events
   ------------ | --------------- |------------ |----------------------- 
   click        | keypress        | submit      | load
   dblclick     | keydown         | change      | resize
   mouseenter   | keyup           | focus       | scroll
   mouseleave   |                 | blur        | unload
    
   EX:$("button").click(function(){
    });

## JQuery Effect
### Hide and Show
   hide and show HTML elements with the hide() and show() or toggle() methods:
   Syntax: $(selector).hide(speed, callback);
           $(selector).show(speed, callback);
           // speed values: "slow", "fast" or milliseconds.
        ```
        $("#hide").click(() => {
            $("p").hide();
        });
        $("#show").click(() => {
            $("p").show();
        });
        ```
### Fading
  Methods | Syntax | Description
  --------|---------|-------------------------
 fadeIn()|$(selector).fadeIn(speed,callback)|fade in a hidden element
 fadeOut()|$(selector).fadeOut(speed,callback)|fade out a visible element
 fadeToggle()|$(selector).fadeToggle(speed,callback)|toggles between fadein and fadeout
 fadeTo()|$(selector).fadeTo(speed,callback)|allows fading to a given opacity


3. Functions:
    - addClass(), removeClass()
    - .html() to add HTML tags and text within an element
        - $("h1").html("Hello World");
    - .css(param1, param2) to change the CSS of an element, 
        - param1 attribute name, param2 attribute value
        - EX: $(".red").css("color", "red");
    - .prop(param1, param2) allows you to adjust the properties of elements
        - param1 property name, param2 property value
        - EX: $("button").prop("disable", true);
    - remove() to remove a HTML element completely
        - EX: $("#ID").remove();
    - appendTo() allows you to select HTML elements and append them to another element
        - EX: $("#ID").appendTo("#ID2");
    - clone() to copy elements
        - EX: $("#ID1").clone().appendTo("#ID2");
    - parent() allows you to access the parent of the selected element
        - EX: $("#ID1").parent().css("background-color", "blue");
    - children() allows you to access the children of the selected element
        - EX: $("#ID1").parent().css("background-color", "red");
    - 



# Reference
- w3schools.com/jquery/
- freecodecamp.org/learn/front-end-libraries/jquery
