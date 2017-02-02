# JavaScript Style Guide #


Use Unix line endings.

Use soft tabs with 4 spaces.

Use `===` and `!==` instead of `==` and `!=` for comparison expressions.


## Naming Conventions ##

### Identifiers Start With a Lowercase Letter and use camelcase for Multiple Words ###

*No*

```js
var _myVar = 'foo';
var my_var = 'foo';
var MYVAR = 'foo';
var $myvar = 'foo';
```

***Yes***

```js
var myVar = 'foo';
```



### Constructors Start With an Uppercase Letter and use camelcase for Multiple Words ###

*No*

```js
function foo() {};

foo.prototype = {};

new foo;
```

***Yes***

```js
function Foo() {};

Foo.prototype = {};

new Foo;
```



## Structure

### Use Single Quotes ###

*No*

```js
var foo = "bar";
```

***Yes***

```js
var foo = 'bar';
```



### Place Opening Brackets on Same Line as Preceding Statement ###

*No*

```js
function foo()
{

}
```

***Yes***

```js
function foo() {

}
```



### Declare all Variables at the top of Their Scope ###

*No*

```js
function sample() {
  
    if ( condition ) {
      
        var foo = 'bar';
    }
    
    return foo;
}
```

***Yes***

```js
function sample() {
    
    var foo;
    
    if ( condition ) {
    
        foo = 'bar';
    }
    
    return foo;
}
```



### Prefer Chained Variable Declarations With Preceding Commas ###

Missing commas in chained variable declarations do not always cause an exception to be thrown. Preceding commas are easier to read when making sure each line has a comma. 

Assignment of Arrays and Objects should not be chained (unless empty) and should use ending commas. Missing commas in these types always cause exceptions.

*No*

```js
var foo;
var bar;
var baz;
var lorem = [ 'value1', 'value2' ];
var ipsum = { value1: 'value1', value2: 'value2' };
```

*No*

```js
var foo, bar, baz, 
  lorem = [ 'value1', 'value2' ],
  ipsum = { value1: 'value1', value2: 'value2' };
```

*No*

```js
var foo,
    bar,
    baz,
    lorem = [ 'value1', 'value2' ],
    ipsum = { value1: 'value1', value2: 'value2' };
```

***Yes***

```js
var foo
    , bar
    , baz
    ;
    
var lorem = [
    'value1',
    'value2'
];

var ipsum = {
    value1: 'value1',
    value2: 'value2'
};
```



### Use Whitespace ###

*No*

```js
function sample(arg,bar){
    var tmp
        ,foo=arg && bar?true:false;
    
    if(foo){tmp=foo;}
    
    if(bar){
        tmp = bar;
    }else if ( baz ) {
        tmp = baz;
    }else{
        tmp = bat;
    }
    return tmp+1-4*6;
}

const methodName = function(arg1,arg2){
	const multiply = arg1*arg2;
	return multiply;}
```

***Yes***

```js
function sample( arg, bar ) {
    
    var tmp
        , foo = arg && bar ? true : false
        ;
    
    if ( foo ) {
    
        tmp = foo;
    }
    
    if ( bar ) {
    
        tmp = bar;
    
    }
    else if ( baz ) {
    
        tmp = baz;
    
    }
    else {
    
        tmp = bat;
    }
    
    return tmp + 1 - 4 * 6;
}

const methodName = function ( arg1, arg2 ) {
	
	const multiply = arg1 * arg2;
	
	return multiply;}
```



### Use a Bang Operator Instead of Wrapping Parenthesis for Immediately Invoked Functions ###

*No*

```js
// ES5
( function () {} )();

// ES6
( () => {} ) ();
```

***Yes***

```js
// ES5
!function () {}();

//ES6
!() => {}();
```


### Favor Object Literal Notation for Grouping Object Members ###

*No*

```js
var foo = {};
foo.prop = 'bar';
foo.method = function() {};
```

***Yes***

```js
var foo = {
    prop: 'bar',
    method: function() {}
}
```

### `for` Loops ###

- Do not use the same variable for subsequent loops
- Set your variable and value before the loop or in the loop declaration (ES5)
- Store your conditional length in a variable unless already an integer
- Same rules apply to for…in loops

*No*

```js
var i;

for ( i = 0; i < array.length; ++i ) {
    
    // first loop code      
}

for ( i = 0; i < secondArray.length; ++i ) {
            
    // second loop code
}
```


***Yes***

*Set variables and values before loop*

```js
var i = 0
    , j = 0
    , firstArrLen = firstArray.length
    , secondArrLen = secondArray.length
    ;
    
for ( ; i < firstArrLen; ++i ) {
    
    // first loop code
}

for ( ; j < secondArrLen; ++j ) {
    
    // second loop code
}
```

*Set variables before loop and values in loop declaration*

```js
var i
    , j
    , firstArrLen
    , secondArrLen
    ;
    
for ( i = 0, firstArrLen = firstArray.length; i < firstArrLen; ++i ) {
    
    // first loop code
}

for ( j = 0, secondArrLen = secondArray.length; j < secondArrLen; ++j ) {
    
    // second loop code
}
```

*Set in loop declaration*

```js
for ( var i = 0, firstArrLen = firstArray.length; i < firstArrLen; ++i ) {
    
    // first loop code
}

for ( var j = 0, secondArrLen = secondArray.length; j < secondArrLen; ++j ) {
    
    // second loop code
}
```

*ES6 block scoping allows for use of same variable identifiers but use different names for clarity*

```js
for ( let i = 0, firstArrLen = firstArray.length; i < firstArrLen; ++i ) {
    
    // first loop code
}

for ( let j = 0, secondArrLen = secondArray.length; j < secondArrLen; ++j ) {
    
    // second loop code
}
```


## Text Editor Settings ##


### Sublime Text ###

  1. Make sure a JavaScript file is your currently viewed file type.

  2. Select Preferences > Settings - More > Syntax Specific - User

  3. Enter the following code:

```js
{
    "tab_size": 4,
    "translate_tabs_to_spaces": true,
    "detect_indentation": true,
    "indent_to_bracket": true
}
```
