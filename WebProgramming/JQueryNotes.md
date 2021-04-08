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

### Animation
Syntax: $(selector).animate({params}, speed, callback); params: defines the CSS properties to be animated.
- Manipulate Multiple Properties
    - EX: $("div").animate({left:'250px', opacity: '0.5'});
- Using Relative Values
    - EX: $("div").animate({left:'250px', height: '+=150px',});
- Using Pre-defined Values like "show", "hide", or "toggle"
    - EX: $("div").animate({height:'toggle'});
- Use Queue Functionality
    - EX:
    ``` 
    var div = $("div");
    div.animate({height:'300px', opcacity:'0.4'}, "slow");
    div.animate({width:'300px', opcacity:'0.4'}, "slow");
    ```

### Stop Animations
Syntax: $(selector).stop(stopAll, goToEnd); Optional stopall parameter specifies whether also the animation queue should be cleared or not

### Chaining
Chaining allows to run multiple JQuery methods on the same element.
EX: $("#p1").css("color", "red").slideUp(2000).slideDown(2000);

## JQuery HTML

### DOM Manipulation
Get Content / Set Content: With parameters is to set content and get content without parameters 
  - <span style="color:red">text()</span> Sets or returns the text content of selected elements
  - <span style="color:blue">html()</span> Sets or returns the content of selected elements
  - <span style="color:blue">val()</span> Sets or returns the value of form fields
*** All three methods come with a callback function with two parameters: the index of the current element in the list of elements selected and the original value.
```
$('#test1').text((i, origText) => {
    return "Old text: " + origText + " New text: Hello Word!
    (index: " + i + ")";
});
```

Get Attributes / Set Attributes:
  - <span style="color:blue">attr()</span> Get Attribute values

Add Elements:
  - append() Insert content at the end of the selected elements
  - prepend() Insert content at the start of the selected elements
  - after() Insert content after the selected elements
  - before() Insert content before the selected elements

Remove Elements / Content:
  - remove() Removes the selected element (and its child elements)
  - empty() Removes the child elements from the selected element 

### CSS Manipulation
  - addClass() Adds one or more classes to the selected elements
  - removeClass() Remove one or more classes to the selected elements
  - toggleClass() Toggles between adding/removing classes  
  - css() Sets or returns the style attribute 
  - Dimension Methods:
      - width() Sets or returns the width of an element(excludes padding, border and margin)
      - hieght() Sets or return the height 
      - innerWidth() return the width (includes padding)
      - innerHeight() return the height (includes padding)
      - outerWidth() return the width (includes padding and border)
      - outerHeight() return the height (includes padding and border)

## Traversing


## AJAX
### Introduction
AJAX is short for Asychronous JavaScript and XML which is used to load data in the background and display it without reloading the whole page.
### Use JQuery for AJAX
The load() method loads data from a server and puts the returned data into the selected element.
Syntax: $(selector).load(URL, data, callback);
  - URL is required specifies the URL you wish to load.
  - Optional data parameter specifies a set of querystring key/value to send along with the request.
  - Optional callback is the name of a function to be executed after the load() method is completed. The callback function has three parameters:
    - responseTxt Contains the resulting content if the call succeeds
    - statusTxt contains the status of the call
    - xhr contains the XMLHttpRequest Object
### HTTP Request: GET vs. POST
The $.get() method requests data from the server with an HTTP GET request.
Syntax: $.get(URL, callback); URL is required, callback is optional

The $.post() method requests data from the server using an HTTP POST request.
Syntax: $.post(URL, data, callback);
# Reference
- w3schools.com/jquery/
- freecodecamp.org/learn/front-end-libraries/jquery
