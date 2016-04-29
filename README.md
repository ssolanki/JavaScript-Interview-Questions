# JavaScript-Interview-Questions

Event Delegation

    The event delegation helps to simplify event handling by smart use of bubbling. 
    It is one of the most important JavaScript patterns.

	The delegation concept:
	
	If there are many element inside one parent, and you want to handle events on them of them - 
	don’t bind handlers to each element.

	Instead, bind the single handler to their parent, and get the child from event.target		

	src: http://javascript.info/tutorial/event-delegation
		http://stackoverflow.com/questions/1687296/what-is-dom-event-delegation

Event Bubbling and Capturing

	DOM elements can be nested inside each other. 
	And somehow, the handler of the parent works even if you click on it’s child.

	The main principle of bubbling states:
	After an event triggers on the deepest possible element, it then triggers on parents in nesting order.

	Stopping Bubbling:
		The bubbling goes right to the top. 
		When an event occurs on an element - it will bubble up to <HTML>, triggering handlers on it’s way.
		event.stopPropagation() or event.cancelBubble used.

	Capturing:
		The event first goes down and then bubbles up. 
	src: http://javascript.info/tutorial/bubbling-and-capturing

Closures 

this

	http://stackoverflow.com/questions/4195970/what-does-this-mean

Inhertiance

	http://www.sitepoint.com/simple-inheritance-javascript/


Check an object is Array or not

	    var a = [1,4,5];
	    console.log(typeof a);	// gives object not array
	    console.log(Array.isArray(a));	// true
	    console.log(Object.prototype.toString.call( a ))	// [object Array]

Strict

	(function() {
	    "use strict";   // Strict mode

	    test("direct");
	    test.call(5, "with 5");
	    test.call(true, "with true");
	    test.call("hi", "with 'hi'");

	    function test(msg) {
	        console.log("[Strict] " + msg + "; typeof this = " + typeof this);
	    }
	})();
	Output:

	[Strict] direct; typeof this = undefined
	[Strict] with 5; typeof this = number
	[Strict] with true; typeof this = boolean
	[Strict] with 'hi'; typeof this = string
	Whereas in loose mode, all of those would have said typeof this = object

Difference between a variable that is: null, undefined or undeclared?
	
	In JavaScript,

	undefined means a variable has been declared but has not yet been assigned a value.

	null is an assignment value. It can be assigned to a variable as a representation of no value.

	Undeclared are variable with no use of var keyword, so It operates as global in window scope.
	Don't care in which scope used first so you can used in outside of a block also.

	src: http://lucybain.com/blog/2014/null-undefined-undeclared/  
