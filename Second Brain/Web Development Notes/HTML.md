--- 

HyperText markup language ->  Is a markup language for the web that defines the structure of web pages

---   

## DOM: Document Object Model

(DOM: Tree Structure that describes how the html elements are related to each others)

## Html Elements

~~~ 
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Hello!</title>
	</head>
	<body>
		Hello, World :)
	</body>
</html>
~~~

## Headings 

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Headings</title>
	</head>
	<body>
		<h1>Heading 1</h1>
		<h2>Heading 1</h2>
		<h6>Heading 1</h6>
	</body>
</html>
~~~

## Lists 

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Lists</title>
	</head>
	<body>
		An Unordered List
		<ul>
			<li>Item</li>
			<li>Another Item</li>
			<li>Yes, Another Item</li>
		</ul>
		An ordered List
		<ol>
			<li>First Item</li>
			<li>Second Item</li>
			<li>Third Item</li>
		</ol>
	</body>
</html>
~~~


## Images 

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Images</title>
	</head>
	<body>
		<img src="cat.jgp" alt="Cat" width="300">
	</body>
</html>
~~~

## Links 

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Link</title>
	</head>
	<body>
		<a href="https://google.com">Click here</a>
	</body>
</html>
~~~

## Table 

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Table</title>
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

## Forms

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Form</title>
	</head>
	<body>
		<form>
			<input type="text" placeholder="Full Name" name="name">
			<input type="submit">
		</form>
	</body>
</html>
~~~

More Forms...

~~~
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>My Web Page!</title>
	</head>
	<body>
		<form>
			<div>
				<input name="name" type="text" placeholder="Name">
				<input name="password" type="password" placeholder="Password">
			</div>
			<div>
				Favorite Color?
				<input name="color" type="radio" value="red"> Red
				<input name="color" type="radio" value="blue"> Blue
				<input name="color" type="radio" value="green"> Green
			</div>
			<div>
				<input name="country" list="countries" placeholder="Country"
				<datalist id="countries">
					<option value="Colombia">
					<option value="Brasil">
					<option value="Venezuela">
					<option value="United States">
				</datalist>
			</div>
		</form>
	</body>
</html>
~~~

