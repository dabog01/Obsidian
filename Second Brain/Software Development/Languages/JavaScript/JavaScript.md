JavaScript is going to enable us to do is to begin to write client-side code

Write code that actually runs inside of the users web browser on the client ----------------------
-------------------------Means--------------------------> Manipulate the DOM!1

## Variables

Container for storing data in JavaScript are calles Variables can be declared in 4 ways:

- Automatically
- Using `var`
- Using `let`
- Using `const`

## Data Types

### JavaScript has 8 Datatypes

1. String  
2. Number  
3. Bigint  
4. Boolean  
5. Undefined  
6. Null  
7. Symbol  
8. Object 

### The Object Datatype

The object data type can contain:

1. An object  
2. An array  
3. A date

## How use JavaScript

Add some programming logic to a web page!

~~~
<script>
</script>
~~~

I'm telling the browser... anything between the 'script' tags should be interpreted as JavaScript code that the browser is going to execute

Try this...

~~~
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
        <script>
            alert("Hello World!")
        </script>
    </head>
    <body>
        Hello, World! :)
    </body>
</html>
~~~


## DOM manipulation

### querySelector()

document.querySelector() -> give us the ability to extract html elements out of the page and manipulate it with javascript

i can ==select a particular element== like this
- .querySelector('tag')
- .querySelector('#id')
- .querySelector('.class')

~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Hello!</title>
    <script>
        function hello() {
            /*
                store the class inside a variable
            */
            let heading = document.querySelector('h1');
            if (heading.innerHTML == 'Hello!') {
                heading.innerHTML = 'Goodbye!';
            } else {
                heading.innerHTML = 'Hello!';
            }
        }
    </script>
</head>
<body>
    <h1>Hello!</h1>
    <button onclick="hello()">Click me</button>
</body>
</html>
~~~

### Event driven programming 

- Kind of things that happen on the web in terms of events that happen...
Example: The user clicks on a button, select something like... a drop-dowm list, scroll through a list, submit a form, etc...

- And with JavaScript we can add event listeners or event handlers
 "When an even happens go ahead and run this particular block of code 

- This way our JavaScript code respond to how the user is interacting with the webpage

~~~
// counter.js

let counter = 0;
function count() {
    counter++;
    document.querySelector('h1').innerHTML = counter;
    if (counter % 10 == 0) {
        /*
        Plug in a variable into a string in JavaScript
        with this sintaxis
        */
        alert(`Count is now ${counter}`)
    }
}
/*
.addEventListener() -> generally takes two arguments
    1. What **event** I want to listen for?
    2. What **function** shoud run when the first event does happen?
        2.1. anonymous function : (anonymous -> cause I never going to refer this function
             by name) declared in the same argument line
*/
document.addEventListener('DOMContentLoaded', function () {
    document.querySelector('button').onclick = count;
});
/*
we add this entire event listener because the
next line of code will cause error if doesnt exist one or the code
is further down in the page cause the content of the DOM
is not loaded yet
*/


/* File called on counter.html */
~~~

~~~
// counter.html

<!DOCTYPE html>
<html lang="en">
<head>
    <title>Counter</title>
    <script src="counter.js"></script>
</head>
<body>
    <h1>0</h1>
    <button onclick="count()">Count</button>
</body>
</html>
~~~

### CSS is also within our reach!

~~~
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Colors!</title>
        <script>
            document.addEventListener('DOMContentLoaded', function() {
                // change color font
                document.querySelectorAll('button').forEach(function(button) {
                    button.onclick = function() {  
                        document.querySelector('#header').style.color = button.dataset.color;
                    }
                });
            });
        </script>
    </head>
    <body>
        <h1 id="header">Choose a color!</h1>
        <!--
            Especial attributes -> my way of saying I want associate some data
            to this particular html elements
            'data-<name>'
         -->
        <button data-color="red">Red</button>
        <button data-color="green">Green</button>
        <button data-color="blue">Blue</button>
    </body>
</html>
~~~

### Common events

Here is a list of some common HTML events:

|Event|Description|
|---|---|
|onchange|An HTML element has been changed|
|onclick|The user clicks an HTML element|
|onmouseover|The user moves the mouse over an HTML element|
|onmouseout|The user moves the mouse away from an HTML element|
|onkeydown|The user pushes a keyboard key|
|onload|The browser has finished loading the page|

The list is much longer: [W3Schools JavaScript Reference HTML DOM Events](https://www.w3schools.com/jsref/dom_obj_event.asp).
### Example!

We're going to code a ToDo List :p

~~~
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>To-Do List!</title>
        <script>
            document.addEventListener('DOMContentLoaded', () => {
                // by default, submit button is disabled
                document.querySelector('#submit').disabled = true;
                document.querySelector('#task').onkeyup = () => {
                    if (document.querySelector('#task').value.length > 0) {
                        document.querySelector('#submit').disabled = false;
                    }else {
                        document.querySelector('#submit').disabled = true;
                    }
                }
                document.querySelector('form').onsubmit = () => {
                    const task = document.querySelector('#task').value;
                    // print it out to the JavaScript console
                    console.log(task);
                    // create a new element that I'm gonna add to my html body
                    const li = document.createElement('li');
                    li.innerHTML = task;
                    document.querySelector('#tasks').append(li);
                    document.querySelector('#task').value = "";
                    document.querySelector('#submit').disabled = true;
                    // I want everything client-side
                    // to stop form from submitting, I prevent submit another web request
                    return false
                }
            })
        </script>
    </head>
    <body>
        <h1>Tasks</h1>
        <ul id="tasks">
        </ul>
        <form>
            <input id="task" placeholder="New Tasks" type="text">
            <input id="submit" type="submit" value="Add Task">
        </form>
    </body>
</html>
~~~

## Local Storage.

Maybe you want to store information such that on subsequent visits were able to utilize the information that was ready store 

>"Way of remembering information for later use"

~~~
localStorage.getItem(key)
localStorage.setItem(key, value)
~~~

Example...

~~~
// counter2.js

if (!localStorage.getItem('counter')) {
    localStorage.setItem('counter', 0);
}
function count() {
    let counter = localStorage.getItem('counter');
    counter++;
    document.querySelector('h1').innerHTML = counter;
    localStorage.setItem('counter', counter);
}
document.addEventListener('DOMContentLoaded', function () {
    document.querySelector('h1').innerHTML = localStorage.getItem('counter');
    document.querySelector('button').onclick = count;
});

/* File called on counter2.html */
~~~

~~~
// counter2.html

<!DOCTYPE html>
<html lang="en">
<head>
    <title>Counter</title>
    <script src="counter2.js"></script>
</head>
<body>
    <h1>0</h1>
    <button onclick="count()">Count</button>
</body>
</html>
~~~

Now, we're able to represent data in a structured way where I have access to a particular value

Useful to... exchange of data!, moving data around  form on service to another... API's

## API's 

---

Application Programming Interface

---

In te context of the web we could think of some well defined structured way to services on the internet to communicate to each other!

Sending Request ----> Receive ==Data in a Structured Format==

### JSON

==Data in a Structured Format== : JSON (JavaScript Object Notation)

>" JSON is a way of transferring data in the form of JavaScript objects "

![[Pasted image 20230611225135.png]]

## Ajax

Asynchronous JavaScript 

> "Even after a page is loaded using JavaScript we can make additional Web Request to ask for additional information either from our own web server or third party web servers?... Ajax Request"



