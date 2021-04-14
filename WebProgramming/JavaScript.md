## Loading JavaScript
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
### async/defer should be standard.
Only user render blocking when you have a specific