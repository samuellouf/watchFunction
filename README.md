# watchFunction
A function to watch a function's response and send events to a listener.

## Installation
To install watchFunction, you can simply add the following code to your HTML page.
```html
<script src="https://samuellouf.github.io/watchFunction/watchFunction.js"></script>
```
If you want to use it online, download [this script](https://samuellouf.github.io/watchFunction/watchFunction.js) and add it in your HTML page.
```html
<script src="watchFunction.js"></script>
```
(replace `watchFunction.js` with the name you gave to the file you just downloaded)

## Usage
> [!NOTE]  
> `watchFunction` checks a function/variable every 8th of a second.
You can use `watchFunction` to watch :
### Functions
I have a function :
```javascript
function getTimeString(){
  let date = new Date();
  return date.getHours() + ':' + date.getMinutes();
}
```
> [!NOTE]  
> It gives the time with the format `HH:MM`

Create a listener :
```
function listener(event){
  // My function's value changed so let's do something about it
  alert(`getTimeString's value changed.\n ${event.old_value}➝${event.new_value}`);
}
```

And add it :
```javascript
watchFunction(getTimeString, listener)
```

> [!NOTE]  
> Since the function `getTimeString()` gives the time with the format `HH:MM`, it will change every minute.

If you wait a minute, you will get an alert popup.
### Variable
I have a variable :
```javascript
var test = null;
```

Create a listener :
```
function listener(event){
  // My function's value changed so let's do something about it
  alert(`test's value changed.\n ${event.old_value}➝${event.new_value}`);
}
```

And add it :
```javascript
watchFunction(() => test, listener)
```

If change your variable's value, you will get an alert popup.
