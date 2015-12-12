# RxJS (Reactive Extensions for JavaScript)


## Reactive Programming

### What does reactive programming help solve? 
Reactive programming offers an approach to think about and handle asynchronous code in an easier and more manageable way. It's an alternative to using callbacks and promises. 

The terms below (Observable, Observer, Operations, Subjects, etc.) are applicable in other languages (i.e. Python, Java, etc.). 


### What is RxJS? 
RxJS is a library that implements reactive programming by allowing you to query and manipulate streams of data. RxJS is specific to JavaScript; however, other languages have their own implementation (i.e. RxJava).


### How can you use RxJS? 


## Functional Programming

### What does functional programming have to do with RxJS? 

Functional programming is the basis for manipulating the data streams that will be available through use of RxJS. Functional programming allows you to abstract common operations that tend to be short and self-descriptive. 


### What is the difference between functional programing and normal way of doing things? 

1. Data in functional programming is immutable; you create new data structures instead of changing the ones that already exist. For example, if you need to manipulate an array, simply create a new one with the new values rather than changing the original.

2. Functional programming is **stateless**, meaning that every task is performed as if for the first time. 

3. The combination of immutability (#1) and statelessness (#2) means that each function is ignorant of other functions in the application. Your function only operates on the data that is passed in as an argument and does not rely on outside values to perform calculations.  



### What are common functions in functional programming?

* map: transforms data
* filter: narrows collections
* concactAll: 
* reduce: turns collection into single value
* zip: combines two collections


### What's the difference between using these common functions in function programming vs. loops? 

**Traversing an Array** 

Using loops to traverse an array: 
	
	var getNames = function() {
		var names = ["Julianne", "Pawan", "Gurpreet"]; 
		
		for (var i=0; i<names.length; i++) {
			console.log(names[i]); 
		}
		
	}
	
Using forEach to traverse an array: 

	var getNames = function() {
		var names = ["Julianne", "Pawan", "Gurpreet"]; 
		
		names.forEach(function(name) {
			console.log(name); 
		});
	}


## Observable

### What is an observable? 
An observable represents a streaming sequence of data (imagine an array), which is separated by *time*. For example, instead of conceptualizing a click event in isolation, imagine click events as a stream of data which can be queried and manipulated.

	[buttonClickEvent1, buttonClickEvent2, buttonClickEvent3]


### What is an example of observable? 
*Example*: Create an Observable of click events, filter out the clicks that happen on the left side of the screen, and then take only the first 10 of those clicks and print their coordinates to the console.*

	Rx.Observable.fromEvent (document, "click")
		.filter(function(c) { return c.ClientX > window.innerWidth / 2)
		.take(10)
		.subscribe(function(c) { console.log(c.clientX, c.clientY })


### What is the difference between an observable and a promise? 
Observbles are lazy, promises are not; promises will run a block of code once you have access to the promise. Observable 


## Observer 
Object in JS that has three functions: 

	1. onNext 
	2. onError 
	3. onComplete 


## Operations


## Subject


## References 
RxJS

* <http://media.pragprog.com/titles/smreactjs/reactive.pdf>


Functional Programming 

* <http://www.smashingmagazine.com/2014/07/dont-be-scared-of-functional-programming/>
