# JQuery 
1. Introduction
    JQuery is a lightweight JS library provides features like
        - HTML/DOM manipulation
        - CSS manipulation
        - HTML event handle
        - Effects and animations
        - AJAX
        - Utilities
2. Use JQuery by download and include it in your file or use CDN
    Here is Google CDN: https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js
3. Basic Syntax: $(selector).action()
    EX: document ready Event:
    ```JQuery
    $(document).ready(function(){
    });

    $(function() {
    });
    ```
4. Selectors: JQuery uses CSS Selectors to target elements.
    JQuery Selectors Reference:
    https://www.w3schools.com/jquery/jquery_ref_selectors.asp
    - By Type: $("button"), $(document)
    - By Class: $(".classname")
    - By ID: $("#IDname")
    - By className:nth-child(n): $(".className:nth-child(3)")
    - By target based on positions using :odd or :even, $(".className:odd")

5. JQuery Syntax For Event
    Some common DOM events:
    Mouse Events | Keyboard Events | Form Events | Document/Window Events
    ------------ | --------------- |------------ |----------------------- 
    click        | keypress        | submit      | load
    dblclick     | keydown         | change      | resize
    mouseenter   | keyup           | focus       | scroll
    mouseleave   |                 | blur        | unload
    EX:$("button").click(function(){
    });

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
