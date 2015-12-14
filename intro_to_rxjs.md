# RxJS (Reactive Extensions for JavaScript)


## Reactive Programming

### What does reactive programming help solve? 
Reactive programming offers a paradigm to handle asynchronous code in an easier and more manageable way. It's an alternative approach to using callbacks and promises. Reactive Extensions makes it easier to glue together and manage different sources of data (UI events, GPS, Twitter feeds, RSS feeds, etc.) through the use of data streams.
 

### What is RxJS? 
RxJS is a library that implements reactive programming by allowing you to query and manipulate streams of data. RxJS is specific to JavaScript; however, other languages have their own implementation (i.e. RxJava). The terms below (Observable, Observer, Operations, Subjects, etc.) are applicable in other languages and their own implementation of the Reactive Extensions library.

**Rx = Observables + LINQ + Schedulers (?)**


### How can you use RxJS? 


## Functional Programming

### What does functional programming have to do with RxJS? 

Functional programming is the basis for manipulating the data streams that will be available through use of RxJS. Functional programming allows you to abstract common operations that tend to be short and self-descriptive. 


### What is the difference between functional programing and normal way of doing things? 

1. Data in functional programming is immutable; you create new data structures instead of changing the ones that already exist. For example, if you need to manipulate an array, simply create a new one with the new values rather than changing the original.

2. Functional programming is **stateless**, meaning that every task is performed as if for the first time. 

3. The combination of immutability (#1) and statelessness (#2) means that each function is ignorant of other functions in the application. Your function only operates on the data that is passed in as an argument and does not rely on outside values to perform calculations.  


### What are common operators useful in RxJs?

* map: transforms data; converts each event on a stream to a new value
* filter: narrows events to only the ones you need
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

An observable represents a sequence of data (imagine an array) made available over *time*. For example, instead of conceptualizing a click event in isolation, imagine click events as a stream of data which can be queried and manipulated.

	[buttonClickEvent1, buttonClickEvent2, buttonClickEvent3]

With observable sequences, we can use push or pull patterns. 
	
* When using a push pattern, we *subscribe* to the source stream and react to the new data as soon as it is available.
* When using a pull pattern, we use operations synchronously. 

### What is an example of using an observable? 
*Example*: Create an Observable of click events, filter out the clicks that happen on the left side of the screen, and then take only the first 10 of those clicks and print their coordinates to the console.*

	Rx.Observable.fromEvent (document, "click")
		.filter(function(c) { return c.ClientX > window.innerWidth / 2)
		.take(10)
		.subscribe(function(c) { console.log(c.clientX, c.clientY })

### What is the difference between an observable and a promise? 
Observables are lazy, promises are not.

### What is the subscribe method? 


## Observer 
Observers receive notifications (while observables send them). 

Observers have three functions: 

	1. onNext 
	2. onError 
	3. onComplete 


	var observer = rx.Observer.create(
		// called for each element in Observable sequence
  		function onNext(result){ 
    		console.log(result); 
  		},
  		// called once in case of error 
  		function onError(err){ 
    		console.log(err); 
  		},
  		// called once when stream finishes
  		function onCompleted(){ 
    		console.log('Completed'); 
  		}
	);
	observable.subscribe(observer);




## Operations


## Subject


## References 
RxJS

* <http://media.pragprog.com/titles/smreactjs/reactive.pdf>

* <https://xgrommx.github.io/rx-book/why_rx.html> 

* <https://channel9.msdn.com/Series/Rx-Workshop/Rx-Workshop-Observables-versus-Events>

* <http://niallconnaughton.github.io/wwc-rx-workshop/> 


Functional Programming 

* <http://www.smashingmagazine.com/2014/07/dont-be-scared-of-functional-programming/>
