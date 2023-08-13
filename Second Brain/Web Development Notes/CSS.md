--- 

Cascading Style Sheets -> Describes how HTML elements are to be displayed on screen

---

## Basic Concepts

### In-line Styling

~~~ 
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Hello!</title>
	</head>
	<body>
		<h1 style="color: blue; text-align: center;">Welcome to my web Page!</h1>
		<h1 style="color: red; text-align: center;">Another heading</h1>
		Hello, World :)
	</body>
</html>
~~~

### Style Element

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Hello!</title>
		<style>
				h1 {
					color: blue;
					text-align: center;
				}
		</style>
	</head>
	<body>
		<h1>Welcome to my web Page!</h1>
		<h1>Another heading</h1>
		Hello, World :)
	</body>
</html>
~~~

==Both examples are useful only in one page==

### Using a .CSS file

~~~
style.html

<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Hello!</title>
		<link rel="stylesheet" href=style.css>
	</head>
	<body>
		<h1>Welcome to my web Page!</h1>
		<h1>Another heading</h1>
		Hello, World :)
	</body>
</html>
~~~

~~~
style.css

h1 {
	color: red;
	align-text: center;
}
~~~

---
## First look at CSS styling

### Size

~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Size</title>
		<style>
			div{
				background-color: orange;
				height: 400px;
				width: 100px;
				padding: 20px;
				margin: 20px;
			}
		</style>
	</head>
	<body>
		<div>
			Hello, World :)
		</div>
	</body>
~~~

### Font

~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Font</title>
		<style>
			div{
				border 3px solid black;
				font-family: Arial, sans-serif;
				font-size: 28px;
				font-weight: bold;	
			}
		</style>
	</head>
	<body>
		<div>
			Hello, World :)
		</div>
	</body>
~~~

### Tables

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Table</title>
		<style>
			table{
				border: 1px solid black;
				border-collapse: collapse;
				}
			tr, th{
				border: 1px solid black;
			}
		</style>
	</head>
	<body>
		<table>
			<thead>
				<tr>
					<th>Ocean</th>
					<th>Average Depth</th>
					<th>Maximum Depth</th>
				<tr>
			</thead>
			<tbody>
				<tr>
					<th>Pacific Ocean</th>
					<th>4,280 m</th>
					<th>10,911 m</th>
				<tr>
				<tr>
					<th>Atlantic Ocean</th>
					<th>3,646 m</th>
					<th>8,486 m</th>
				<tr>
			</tbody>
		</table>
	</body>
</html>
~~~

### Hover

~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Size</title>
		<style>
			button{
				background-color: orange;
				height: 50px;
				width: 200px;
				font-size: 24px;
			}
			button:hover{
				background-color: green;
			}
		</style>
	</head>
	<body>
		<div>
			<button>Click Me!</button>
		</div>
	</body>
~~~


---

## Id's & Classes

### Style-id

~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Size</title>
		<style>
			#foo, #bar{
				color: blue;
			}
		</style>
	</head>
	<body>
		<div>
			<h1 id="foo">Heading 1</h1>
			<h1>Heading 1</h1>
			<h1>Heading 1</h1>
		</div>
	</body>
~~~

### Style-class

~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Size</title>
		<style>
			.baz{
				color: blue;
			}
		</style>
	</head>
	<body>
		<div>
			<h1 class="baz">Heading 1</h1>
			<h1 class="baz">Heading 1</h1>
			<h1>Heading 1</h1>
		</div>
	</body>
~~~


## Specificity

Hierarchy/Rank that determines which element style declaration is ultimately applied to an element
1. inline
3. id
4. class
5. type

## CSS Selectors

### **Types**

| Interaction | Selector Type |
| ----------- | ----------- |
| a, b | Multiple Element Selector |
| a b | Descendant Selector|
| a > b | Child Selector |
| [a = b] | Atribute Selector |
| a : b | Pseudo-class Selector |
| a :: b | Pseudo-element Selector |

#### Descendant

All descendant elements

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Lists</title>
		<style>
			ul li {
				color: blue;
			}
		</style>
	</head>
	<body>
		<ol>
			<li>First Item</li>
			<li>Second Item</li>
			<ul>
				<li>Sublist item one</li>
				<li>Sublist item two</li>
				<li>Sublist item three</li>
			</ul>
			<li>Third Item</li>
		</ol>
	</body>
</html>
~~~

#### Atribute

~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Hello</title>
		<style>
		a {
			color: blue;
		}
		a [href="https://facebook.com"] {
			color: red;
		}
		</style>
	</head>
	<body>
		<ul>
			<li><a href="https://google.com">Goggle</a></li>
			<li><a href="https://facebook.com">Facebook</a></li>
			<li><a href="https://amazon.com">Amazon</a></li>
	</body>
</html>
~~~

