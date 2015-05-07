#Vanilla Javascript
Up, up, up and away from jQuery.

See: http://toddmotto.com/is-it-time-to-drop-jquery-essentials-to-learning-javascript-from-a-jquery-background/ for original article.

##DOM Selection

###Class Selectors
See: https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName
```javascript
var elements = document.getElementsByClassName(names);
var elements = rootElement.getElementsByClassName(names);
```
Support: ie.9


###ID Selectors
See: https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById
```javascript
var element = document.getElementById(id);
```
Support: ie.5.5


###Tag Selectors
See: https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName
```javascript
var elements = document.getElementsByTagName('div');
```
Support: ie.6


###Query Selectors
querySelector/querySelectorAll

This is the all powerful selector...

See:
- https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll
- https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll

```javascript

/* Classes */
// Get the first .myClass class name
document.querySelector('.myClass');

// Return a NodeList of all instances of .myClass
document.querySelectorAll('.myClass');

/* ID */
// Get the myID id
document.querySelector('#myID');

/* Tags */
// Return a NodeList of all 'div' instances
document.querySelectorAll('div');

/* Complex selectors */
// Get the last list Node of .someList unordered list
document.querySelector('ul.someList li:last-child');

// Get some data-* attribute
document.querySelectorAll('[data-toggle]');
```

- Available as ```Document.``` and ```Element.```
- ```Element.querySelectorAll``` returns a **_non-live_** NodeList
- See also https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector for string argument CSS syntax

Support: ```Document.``` = ie.9 *(ie.8 - CSS2 Selectors only)*. ```Element.``` = ie.8





##Class manipulation

###Add class
```javascript
var div = document.querySelector('div');
div.classList.add('myClass');
div.classList.add("foo","bar"); //add multiple classes
```


###Remove class
```javascript
var div = document.querySelector('div');
div.classList.remove('myClass');
```


###Toggle class
```javascript
var div = document.querySelector('div');
div.classList.toggle('myClass');
```


###Contains class
```javascript
var div = document.querySelector('div');
console.log(div.classlist.contains('myClass'));
```
Support: ie.10 see: https://developer.mozilla.org/en-US/docs/Web/API/Element/classList for polyfill


## Array itteration

Replacing jQuery's ```$.each(myArray, function(i){ //.... });``` and ```$('').each(function(i){ //.... });```


###Array.prototype.forEach
See: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach

```javascript
// Chain onto array
['a', 'b', 'c', 'd'].forEach(function(element, index, array){
  // ...
});

// Or
var myArray = ['a', 'b', 'c', 'd'];
myArray.forEach(function(element, index, array){
  // ...
});

//Note: Empty members are not visited
```
Support: ie.9


###Traditional Array looping and closure
```javascript
var myArray = ['a', 'b', 'c', 'd'],
    l = myArray.length,
    i;
for (i=0; i<l; i++) {
  (function(index){
    // The scope of i is now captured via index param if need to use 'later' in event handlers e.g.
    myArray[index].addEventListener('click', function(index){console.log(index);}, false);
  })(i);
}
```


###NodeList looping
To loop requires a traditional for loop.
See: https://developer.mozilla.org/en/docs/Web/API/NodeList
```javascript
// Add a class to every Node in the NodeList
var elements = document.querySelectorAll('.element'); //Or document.getElementsByClassName('element');
for (var i = 0; i < elements.length; i++) {
  elements[i].classList.add('myClass');
}
```


##Attributes getting, setting and removing

```javascript
console.log(document.querySelector('.myClass').getAttribute('data-abcd'));
document.querySelector('.myClass').setAttribute('data-abcd', 'my data string');
document.querySelector('myClass').removeAttribute('disabled');
```

###Boolean attributes
There are 2 'correct' ways of setting Boolean attributes:
1. Via ```setAttribute``` with an empty string value
2. Via element properties ```element.attribute = ``` which is probably(?) *cleaner*

```javascript
document.querySelector('.myClass').setAttribute('disabled', ''); // Correct
document.querySelector('.myClass').disabled = true; // Cleaner(?)
```


##JSON Parsing
```javascript
<div class="element" data-info='{ "name" : "abc", "id" : "123" }'></div>

var data = JSON.parse(document.querySelector('.element').getAttribute('data-info'));
console.log(data.name);
console.log(data.id);
```

##CSS manipulation
Done via HTMLElement.style.

See: https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style

```javascript
element.style.color = "ff00ff";  // Directly
//Or
var st = element.style;
st.color = "#00ff00";  // Indirectly
```

##Document ready event
```javascript
document.addEventListener('DOMContentLoaded', function() {
    // DOM is now ready....
    console.log('...hello');
}, false);
```
Support: ie.9

####Links
- a
- b
