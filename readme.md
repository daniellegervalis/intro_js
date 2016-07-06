# LEARNING OBJECTIVES
- Describe the role Javascript plays alongside HTML and CSS.
- List and describe the primitive data types.
- Describe uses of mathematical operators in Javascript.
- Define type coercion.
- Define and use complex data types.
- Explain the difference between `prompt` and `console.log`
- Practice proper JS syntax and semantic variable naming.
- Describe why control flow is utilized in computer programming
- Write an if, else if, and else statement in JS
- Write a for loop and while loop in JS and differentiate between them
- Utilize loops to iterate through complex data types

# HTML, CSS and Javascript (20/20)
HTML (content), CSS (style) and Javascript (behavior) as the main components of front-end web development.


##Identify Javascript features in Cookie Clicker.
* 2 minutes: Go look at [Cookie Clicker](http://orteil.dashnet.org/cookieclicker/) . Play with it. Think about what's allowing these behaviors to exist.

### Findings
- Interactivity
  - Click something, something happens.
    - Like: increment Like counter.
    - Comment: submit comment, appended to post.
  - Javascript defines what happens on a page depending on how you interact with it.
- No Refreshes / User Experience
  - When I click a cookie, CC is able to increment and update the counter on the page without a hard refresh.
  - When I comment on a post, Facebook is able to process my new comment and render it on the page without refreshing the entire page.
  - Gives the page a much smoother user experience compared to a static page that doesn't have this sort of functionality.
- Communication with a server
  - Javascript is somehow telling a server that (a) a user has done something, (b) save that interaction and (c) display the results of that interaction to all other users.

This is not an exhaustive list of Javascript properties, but we'll go over these and more in more detail later on in the course.

So, to sum up the main three components of front-end web development up in one word each...
- HTML: Structure
- CSS: Styling
- Javascript: Behavior

# JS: The Client-Side Programming Language of the Web

- Brief history: Created in 10 days by Brendan Eyck, of Mozilla. *Not* related to Java in any way but its name.
  - "Java" is to "Javascript" as "ham" is to "hamster"

- What's a programming language?
  - What can it do that a markup language like HTML can't?
  - It let's us do things! It lets us act on information, manipulate it, display it, pretty much whatever we want.
- Javascript enables us to do all that in a browser.
  - Using the tools you learned in the pre-work (e.g., data types, loops, functions).

## Why is it the dominant programming language of the web?
- Barriers to entry for learning Javascript are very low.
  - No additional software required to run it. Just a text editor and a browser.
    - You can even run it directly in the browser via its Javascript console.
      - Ex. Hide images on the GA website.
      - You'll learn more about the browser Javascript console when you start adding Javascript to the websites you make in this class.
- On top of that, it's supported by all web browsers.
- Javascript has evolved since its creation.
  - One of the biggest additions to JS was AJAX, which allows use to reload parts of a page without refreshing the entire thing (just like on Facebook). Big implications for User Experience.
- A lot of frameworks and libraries -- like Backbone and jQuery -- have emerged that enable us to do so much more -- and do it quickly -- with Javascript.

# Setting up our environment

## First, create your HTML and JS

- `index.html` and `script.js`

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Yo</title>
  </head>
  <body>
  <script src="script.js"></script>
  </body>
</html>
```
You can also put your script tag in the head. Putting the tag in the body ensures that the rest of the page loads before your script files run. However, [HTML5 has two new attributes ](http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html) that allow for more control in how scripts run, regardless of whether they're place in the head or body.

## Next, open the site in Chrome, and open the Dev Tools

- Command + Option + I
- The "Console" is a REPL
  - “Read-Eval-Print Loop”.
  - Programming environment that lets us run Javascript code one line at a time.
  - What does it do?
    1. (R)eads our code.
    2. (E)valuates it.
    3. (P)rints it to the console.
    4. Then it (L)oops back to the beginning, ready to (R)ead the next line of code we feed it.
  - Primarily used for testing and debugging.

> `⌘ + ⌥ + i` enters you in the the chrome dev tools(if you're using chrome...) Here you can do a bunch of stuff like inspect elements and look at the html. More importantly for this class though, is it allows you to access the console which interacts with the JS you loaded to your page. In our case we'll see that interaction with the code below

In your `script.js` file add the following:
```js
console.log("hello world")
```

> console.log() is just a way to display something in  our REPL.  

# Primitive Data Types

## Intro
Primitive data types are the building blocks of Javascript.
- Whenever you do anything in Javascript, you are creating and changing these basic pieces of information.

There are five primitive data types.

### What are they?

  1. Numbers
  2. Strings
  3. Booleans
  4. Undefined
  5. Null

We store data types in variables. A variable is a "bucket" that holds data. You can pass the bucket around, empty it, refill it, etc.

- Format: `var NAME = DATA;`

  ```javascript
  // For example...
  var myClass = "intro";

  // After instantiation you can then reference variables by just their name, without "var".
  myClass;
  => "intro"

  // Variables can not only store single data types but also expressions.
  var multiplication = 5 * 2;
  => 10
  ```

- Javascript is a "dynamic" or "untyped" language, meaning a variable can switch between data types.

  ```javascript
  // This change is valid in Javascript.
  var myFavoriteNumber = 5;
  var myFavoriteNumber = "five";
  ```

## Numbers

In Javascript, numbers are numerical values -- straightforward!
  - All numbers are of type "number," regardless of format (e.g., integer, float/decimal).

  ```javascript
  // The "typeof" operator returns the data type of a value
  typeof 5;
  => "number"

  typeof 5.5;
  => "number"
  ```

Operations
- Math in Javascript follows the same rules you've known since elementary school math.
- Basic operators: `+, -, *, /`

  ```javascript
  // Addition
  10 + 2;
  => 12

  // Subtraction
  10 - 2;
  => 8

  // Multiplication
  10 * 2;
  => 20

  // Division
  10 / 2;
  => 5
  ```

- Order of precedence: P(E)MDAS (Parentheses, Multiplication, Division, Addition, Subtraction)

  ```javascript
  // This would be interpreted as...
  // Go through step by step with class.
  ( 4 + 2 ) * ( 12 / 3 );
  => 6 * 4
  => 24

  // How would this be interpreted?
  // Like operators are processed from left-to-right. In this case, division happens before multiplication.
  ( 8 / 4 * 2 ) + 1
  => ( 2 * 2 ) + 1
  => 5
  ```

- % (Modulus)
  - Returns the remainder of a division operation.

    ```javascript
    // What is the remainder of 12 / 5?
    12 % 5;
    => 2
    ```

  - Q: Modulus has a pretty handy use case: to check if a number is even.
    - A number is even if it is divisible by 2.
    - Check if a number is even: `NUMBER % 2`
      - What should this return?

      ```javascript
      // Returns 0 if even.
      4 % 2;
      => 0

      // Returns 1 if odd.
      5 % 2;
      => 1
      ```

### NaN ("Not a number")
- A special number...that's not a number?

    ```javascript
    typeof NaN
    => "number"
    ```

  - You usually get NaN when the result of a math operation is not real (e.g., dividing 0 by 0, multiplying strings together).

    ```javascript
    0/0;
    => NaN
    ```

- You can test whether a value is a valid number using the `isNaN()` function.

```javascript
// isNaN returns false if used on a valid number.
var myFavoriteNumber = 5;
isNaN( myFavoriteNumber );
=> false
```

## Undefined & Null
Values that indicate the lack of a meaningful value.
- Anybody else find that weird? How is there more than one data type for nothing?
- Q: What's the difference?

Undefined: automatically applied to a variable with no value.  

```javascript
// A primitive data type of type undefined with only one value: "undefined".
typeof undefined;
=> "undefined"

// Any property that has not been assigned a value is "undefined".
var nothing;
=> undefined

// A function with no defined return value has a return value of "undefined".

// You won't find yourself assigning "undefined" to a value. That's where "null" comes in.
var nothing = undefined;
```

Null: an explicitly-assigned non-value.
  - Javascript will never set anything to `null` by itself. `null` only appears when you tell it to.
  - If I'm not mistaken, the only thing that's inherently `null` in Javascript is `null` itself!
  - Can you imagine a situation where that would be useful?
    - Placeholder for a variable that you know will be replaced with an actual value later on.


So the main difference between `undefined` and `null` is intention. Other than that, they're both...nothing.

### Type Coercion
Javascript will try to make sense of any strange operations you throw at it.
- By "strange", I mean subtracting a number from a string, or multiplying `null` by 100.
- It does this through something called "type coercion" -- converting data types.

You might encounter this when dealing with numerical values but for whatever reason some of them are in string form.

```javascript
// In some cases Javascript is helpful and converts strings to numbers in the correct way.
"3" - "2"
=> 1

// ...but sometimes it doesn't. In this example, the + operator acts as if it's concatenating two strings.
"3" + "2"
=> 32

// And this?
"five" * 5;
=> NaN
```

When in doubt, convert data types that should be numbers using `parseInt()`.

```javascript
// parseInt converts a string to a number value, if available.
parseInt( "3" );
=> 3

parseInt( "burrito" );
=> NaN
```

There are other examples of type coercion, but the point here isn't to remember them all. Just be aware that sometimes Javascript will fire weird results back at you with no explanation. Sometimes, type coercion might be the culprit.

## Strings
Strings are words in javascript!

We instantiate strings using the "string literal" form.

```javascript
// Can use single quotes to instantiate a string...
var greeting = 'Hello!';

/// ...or double quotes.
var greeting = "Hi there!";
```  


### Concatenation
- Like numbers, you can add strings together using `+`.

  ```javascript
  var city = "Washington, ";
  var state = "DC";
  var address = city + state;
  => "Washington, DC"
  ```

- You can't, however, use other math operators on strings.

  ```javascript
  // Q: What do you think happens when we try to subtract strings from each other?
  // When using the "-" operator, the operands are treated as numbers.
  "hamburger" - "ham"
  => NaN

  // The same goes for multiplication and division.
  "hamburger" * 3
  => NaN
  ```

String methods
- Javascript comes with methods you can use to inspect and modify strings.
- Examples:

  ```javascript
  // .search(): find the starting index of a string value.
  // String indexes are 0-based, so the index of a string's first character is 0.
  var greetings = "Hi there Nayana!";
  greetings.search( "Nayana" );
  => 9

  // .slice(): return and store a portion of a string.
  var greetings = "Hi there Nayana!";
  var buddy = greetings.slice( 9, 15 );
  => "Nayana"
  ```

- More examples [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

# Syntax & Semantic Naming

## Syntax
Variable syntax
- Should be named using camelCase lettering.
  - First letter of first word lowercase. First letter of remaining words uppercase.
  - No spaces or punctuation between words.

  ```javascript
  // camelCase
  var pizzaTopping = "pepperoni";
  ```

Semicolons
- General practice is to end every line with a semi-colon.
- Usage depends on the developer.

Comments
- Q: Why would you use comments?
  - Talked about this in the HTML class. Same reasoning applies.
- Types of comments
  ```javascript
  // Single line

  /*
    Multiple
    line
    comments
  */
  ```

- Use to explain the purpose or reasoning behind a piece of code.
- Help out other developers and future you.
  - If anything, it will help us out when grading your projects!

# Prompt

We've learned a lot about basic data types, but it'd be nice if we had a way of getting user input into our browser! We'll learn some ways to use forms and such later in the course, but for now, we'll be getting user input using the `prompt()` function.

At any point in our JS code, if we write `prompt()`, a pop up box will open in our browser for a user to enter in text.

```js
// prompts user and stores value in the variable
var valueOfPrompt = prompt()
// logs value stored
console.log(valueOfPrompt)
```

You can also pass in a string as an argument to have the pop up box contain that string as a ... prompt.

```js
var age = prompt("How old are you?")
```

# Composite Data Types

Composite data types are collections that allow us to store multiple data types.
- There are two kinds in Javascript. What are they?

## Arrays
- Ordered collection of related data types.
- Organized by index.
  - Indexing begins at 0 (e.g., first element in an array has an index of 0, the second has an index of 1, and so on).

Here's how you create an array:  

```javascript
// Instantiate with an array literal.
var mountRushmore = [ "Washington", "Jefferson", "Roosevelt" ];
```

Accessing array values...  

```javascript
// Indexing begins at 0.
// How do I access the first, second and third elements of the array?
mountRushmore[0];
=> "Washington"
mountRushmore[1];
=> "Jefferson"
mountRushmore[2];
=> "Roosevelt"

mountRushmore.push("Lincoln");

mountRushmore[3];
=> "Lincoln"

// You can also place arrays within arrays.
var letters = [ ["a","b","c"], ["d","e","f"], ["g","h","i"] ];

// How would I go about accessing the letter "f" in the above array? Walk me through it.
letters[1][2];
=> "f"
```

Array methods
- There are a lot of useful methods that come with Javascript we can use to inspect and modify arrays. To learn what some of them are...
  - `.length`
  - `.push`
  - `.indexOf`
  - `.reverse`

> There are many more, but these are the most widely-used.

- Documentation
  - [MDN Array Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
  - Navigating documentation is a great skill to have. Some sets of documentation are harder to navigate than others, but if you have a sense of how to dig through a massive trove of information like MDN or RubyDocs, you'll become a much more efficient programmer.

## Booleans
Two values: `true`, `false`.  To be clear, these are not strings, but the concepts of true and false.

Oftentimes you'll be producing boolean values when comparing two values
- Comparison operators: `==`, `===`, `<`, `>`, `<=`, `>=`

```javascript
1 === 1
=> true

1 === 2
=> false

1 == "1"
=> true
```

> What is the differences between the last two? When using `===`, it checks for both the data type and value. `==` only checks for value. Under the hood, though, `==` converts the data type to the same data type and then executes comparison.


## Comparison Operators

- `&&`
- `||`
- `!`

What do the following evaluate too? (ST-WG)

```js
true && false
true || false
5 > 12 && 12 >= 12
17 > 12 || 4 <= 4
```

Let's check out comparison operators in node. node is a server side Javascript environment. We'll talk more about it later in the course.

- `<`, `<=`
- `>`, `>=`
- `!=`, `!==`
- `==`, `===`

```javascript
55 == "55"
=> true
55 === "55"
=> false
```

## Conditionals

Let' talk through the following code (10m)

```javascript
var age = 24;
if(age < 18) {
  console.log("You're too young to enter this club! Get outta here")
}
else if(age >= 18 && age < 21){
  console.log("Come on in! But no Drinking!!")
}
else{
  console.log("Come on in!")
}
```

Conditionals will always follow this pattern. There is a key word(if, else if, else). Followed by an expression that will evaluate to true or false in parentheses. Then followed by code to execute when condition is met.


## Loops

### For loop
There are two ways to write a for loop.

#### The first:

```javascript
for(var i = 0; i < 10; i++){
  console.log(i)
}
```
The first part is the keyword `for`.
Followed by 3 parts `;` separated in parentheses.
- The first part instantiates the iteratee. Essentially gives you access to this value in your code block as i. It starts at 0 in this case.
- The second part is the comparison expression. That means this code will continue to execute until this expression evaluates to false.
- The third and final part is how much the iteratee is incremented after each execution of the loop

#### The second:

```javascript
// instantiate an array of names
var names = ["tyler", "nayana", "andy", "adrian", "nick", "jesse", "james"]
for(i in names){
  console.log(names[i])
}
```

- Again this for loop starts with the keyword `for`.
- In parentheses contains the iteratee followed by the keyword `in` followed by the complex data type you would like to iterate over(array or object)
- In the brackets contains the code you would like executed for each iteration of the loop


### While Loop(15m)
```javascript
var i = 0;
while(i < 10){
  console.log(i)
  // don't increment at first
}
```

### Additional Exercises

[Temp Converter](https://github.com/ga-wdi-exercises/temperature_converter)  

[Fizzbuzz](https://github.com/ga-wdi-exercises/fizzbuzz_js)

[Choose your own adventure](https://github.com/ga-wdi-exercises/choose_your_own_adventure_js)
