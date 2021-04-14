# Loading JavaScript
### Default Behavior
Browser stops rendernig when JavaScript is encountered.JavaScript is executed before rendering continues. Often referred to as content blocking.
HTML Parsing #####      ######
JS Download       ###
JS Execution         ###

### async
Browser downloads JS in parallel whilte HTML renders. When JS is fully loaded, rendering stops whilte JS is executed.
HTML Parsing #####   ######
JS Download    ###
JS Execution      ###
* Should be used when you don't really care about render blocking.

### defer
Browser downloads JavaScript in parallel while HTML renders, then defers execution of JavaScript until HTML rendering is complete.
HTML Parsing ###########
JS Download    ###
JS Execution             ###
- EX: <script src="main.js" defer></script>

### async/defer should be standard.
Only user render blocking when you have a specific

### JavaScript modules
When you wanna use pieces of JS code from another JS file. You can use JavaScript modules.
EX: 1. ```import browser from './browser.js' in the JS file```
    2. In the HTML, ```<script type="module" src="script.js"></script>

# JavaScript Object
Each object is a unique instance of an object prototype.
EX:
```
const backpack = {
    name: "Everyday Backpack",
    volume: 30,
    color: "grey",
    pocketNum: 15,
    strapLength: {
        left: 26,
        right: 26,
    },
    lidOpen:false,
    toggleLid: function(lidStatus) {
        this.lidOpen = lidStatus;
    },
    newStrapLength: function(lengthLeft, lengthRight) {
        this.strapLength.left = lengthLeft;
        this.strapLength.right = lengthRight;
    },
};
```
### Object containers
Objects are typically constants. We can change the properties of the object inside the variable. We can't remove or replace the object from the variable.

### Accessing object properties
dot notation: object.propertyname
bracket notation: object["propertyname"]
* You can use variable with bracket notation. EX: ``` var query = "propertyname"; object[query];

### Define getters and setters
- defined using obejct initializer:
```
var o = {
    a: 7,
    get b() {
        return this.a + 1; // If you omit the this keyword, a will be treated as a new variable
    },
    set c(x) {
        this.a =  x/2;
    }
};
```
- added later to any object at any time using a getter or setter adding method
```
var o ={a:0};

Object.defineProperties(o, {
    'b':{get:function() {return this.a + 1;}},
    'c':{set:function(x) {this.a = x/2;}}
})
```