## Create Custom Event

```javascript
// emitter.js
function MyEmitter() {
	this.events = {};
}

MyEmitter.prototype.on = function(type, listener) {
	this.events[type] = this.events[type] || [];
	this.events[type].push(listener);
};

MyEmitter.prototype.emit = function(type) {
	if(this.events[type]){
		this.events[type].forEach(fn => fn());
	}
};


module.exports = MyEmitter;

// app.js
const Emitter = require('./emitter');
let m = new Emitter();
m.on('greetMe', function() {
	console.log("You greeted Me!");
});

m.emit('greetMe'); // You greeted Me!
```

## Node JS event emitter

```javascript
var emitter = require('events');

emitter.on('mygreet', function(data){
	// listen
});

emitter.emit('mygreet', data);
```

## Inherit NODE JS event emitter

```javascript
// emitter.js
const EventEmitter = require('events');
module.exports = class MyEmitter extends EventEmitter {
	greet(data) {
		this.emit('greet', data);
	}
}

// app.js
var Emitter = require('./emitter');
var m = new Emitter();
m.on('greet', function(data){
	console.log(data);
});
m.greet('my data');
````

## OR inhert using util.inherit

```
const util = require('util');
const EventEmitter = require('events');

function MyGreeter() {
	this.greeting = 'hello me';
}

util.inherits(MyGreeter, EventEmitter);

MyGreeter.prototype.greet = function(data){
	this.emit('greet', data)
};
```
