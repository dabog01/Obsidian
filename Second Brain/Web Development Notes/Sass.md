--- 

**(Syntactically Awesome Stylesheet)**

>"Sass lets you use features that do not exist in CSS, like variables, nested rules, mixins, imports, inheritance, built-in functions, and other stuff."

- Sass is an extension to CSS
- Sass is a CSS pre-processor
- Sass is completely compatible with all versions of CSS
- Sass reduces repetition of CSS and therefore saves time

---
## How to use? 

### Before Sass

~~~
<!DOCTYPE html>
<html lang="en">
	<head>unordered item
		<title>Hello!</title>
		<style>
			ul {
				font-size: 14px;
				color: red;
			}
			ol {
				font-size: 18px;
				color: red;
			}	
		</style>
	</head>
	<body>
		<ul>
			<li>unordered item</li>
			<li>unordered item</li>
			<li>unordered item</li>		
		</ul>
		<ol>
			<li>first item</li>
			<li>second item</li>
			<li>thirth item</li>
		</ol>
	</body>
</html>

~~~

---
### Sass is a different language!!

Require another extension .scss

~~~
// variables.scss

$color: red;

ul {
	 font-size: 14px;
	 color: $color
}

ul {
	 font-size: 14px;
	 color: $color
}

ul {
	 font-size: 14px;
	 color: $color
}
~~~ 

~~~
// variables.html

<!DOCTYPE html>
<html lang="en">
	<head>unordered item
		<title>Hello!</title>
		<link rel="stylesheet" href="variables.scss">
	</head>
	<body>
		<ul>
			<li>unordered item</li>
			<li>unordered item</li>
			<li>unordered item</li>		
		</ul>
		<ol>
			<li>first item</li>
			<li>second item</li>
			<li>thirth item</li>
		</ol>
	</body>
</html>

~~~

==This will do nothing :p==

Because...

### **We need compile the .scss file to generate a .css file**

**Terminal**

~~~
// Installing Sass
npm install -g scss
~~~

~~~
// Complile
sass --watch style.scss style.css
~~~

### After Sass

We change the name of the href file

~~~
// variables.html

<!DOCTYPE html>
<html lang="en">
	<head>unordered item
		<title>Hello!</title>
		<link rel="stylesheet" href="variables.css">
	</head>
	<body>
		<ul>
			<li>unordered item</li>
			<li>unordered item</li>
			<li>unordered item</li>		
		</ul>
		<ol>
			<li>first item</li>
			<li>second item</li>
			<li>thirth item</li>
		</ol>
	</body>
</html>
~~~

---

## Nesting 

~~~
// nesting.scss

div {
	front-size: 18px;
	
	p { 
		color: blue;
	}
	
	ul {
		color: green;
	}
}
~~~ 

~~~
// nesting.html

<!DOCTYPE html>
<html lang="en">
	<head>
		<title>My Web Page!</title>
		<link rel="stylesheet" href="nesting.css">
    </head>
    <body>
        <div>
            <p>This is a paragraph inside the div</p>
            List Inside the div
            <ul>
                <li>Item one</li>
                <li>Item two</li>
                <li>Item three</li>
            </ul>
        </div>
        <p>This is s paragraph outside of the div</p>
        List outside of the     div:
        <ul>
            <li>Item one</li>
            <li>Item two</li>
            <li>Item three</li>
        </ul>
    </body>
</html>
~~~

## Inheritance

~~~
// inheritance.html

<!DOCTYPE html>
<html lang="en">
	<head>unordered item
		<title>Hello!</title>
		<link rel="stylesheet" href="variables.css">
	</head>
	<body>
		<div class="error error--serious"></div>
	</body>
</html>
~~~

~~~
// inheritance.scss

.error {
	border: 2px rgb(144, 0, 255);
	backgound-color: rgb(101, 18, 18);
}

.error-serious {
	border-width: 3px;
}
~~~