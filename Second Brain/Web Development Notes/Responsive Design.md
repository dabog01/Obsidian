--- 

Is the approach that suggests that design and development should respond to the user’s behavior and environment based on screen size, platform and orientation.

Some resourses

1. viewport
2. Media queries
3. Flexbox
4. Grids

--- 

## Viewport

>Visual part of the screen that the user can actually 

~~~
//Inside the head section

<meta name="viewport" content="width=device=width, initial-scale=1.0">
~~~

## Media queries

>How our page is going to look depending of how we render that particular page or what size we're rendering that page on

~~~ 
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Hello!</title>
		<style>
			@media (min-width: 600px){
				body {
					backgound-color: red;
				}
			}
			@media (max-width: 599px){
				body {
					backgound-color: blue;
				}
			}
		</style>
	</head>
	<body>
		Hello, World :)
	</body>
</html>
~~~

## Flexbox 

~~~ 
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Hello!</title>
		<style>
			#container {
				display: flex;
				flex-wrap: wrap;
			}
			$container > div {
				background.color: springgreen;
				font-size: 24px;
				margin: 20px;
				padding; 20px;
				width: 200px;
			}
		</style>
	</head>
	<body>
		<div id="container">
			<div>1. This is some sample text for this div</div>
			<div>2. This is some sample text for this div</div>
			<div>3. This is some sample text for this div</div>
			<div>4. This is some sample text for this div</div>
			<div>5. This is some sample text for this div</div>
			<div>6. This is some sample text for this div</div>
			<div>7. This is some sample text for this div</div>
			<div>8. This is some sample text for this div</div>
			<div>9. This is some sample text for this div</div>
			<div>10. This is some sample text for this div</div>
		</div>
	</body>
</html>
~~~

## Grid 

~~~ 
<!DOCKTYPE html>
<html lang="en">
	<head>
		<title>Hello!</title>
		<style>
			#grid{
				backgound-color: green;
				display: grid;
				padding: 20px;
				grid-column-gap: 20x;
				grid-row-gap: 10x;
				grid-template-columns: 200px 200px auto;
			}
			
			.grid-item{
				background-color: white;
				font-size: 23px;
				padding: 20px;
			}
		</style>
	</head>
	<body>
		<div id="grid">
			<div class="grid-item">1</div>
			<div class="grid-item">2</div>
			<div class="grid-item">3</div>
			<div class="grid-item">4/div>
			<div class="grid-item">5</div>
		</div>
	</body>
</html>
~~~