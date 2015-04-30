#Vanilla Javascript
Up and away from jQuery

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
div.classlist.remove('myClass');
```

###Toggle class
```javascript
var div = document.querySelector('div');
div.classlist.toggle('myClass');
```

###Contains class
```javascript
var div = document.querySelector('div');
console.log(div.classlist.contains('myClass'));
```

Support: ie.10 see: https://developer.mozilla.org/en-US/docs/Web/API/Element/classList for polyfill



####Links
- http://toddmotto.com/is-it-time-to-drop-jquery-essentials-to-learning-javascript-from-a-jquery-background/
- a
