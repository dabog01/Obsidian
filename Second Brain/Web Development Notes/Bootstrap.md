 --- 

Bootstrap is the most popular CSS Framework for developing responsive and mobile-first websites.

https://getbootstrap.com/

---

## Add some bootstrap :)

~~~ 
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap demo</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">
  </head>
  <body>
    <h1>Hello, world!</h1>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-geWF76RCwLtnZ8qwWowPQNguL3RmwHVBC9FhGdlKrxdiJJigb/j/68SIy3Te4Bkz" crossorigin="anonymous"></script>
  </body>
</html>
~~~

## Alerts

~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Hello!</title>
	    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">
	</head>
	<body>
		Hello, World :)
		<div class="alert alert-primary" role="alert">
			A sample primary alert-check it out!
		</div>
		<div class="alert alert-danger" role="alert">
			A sample primary alert-check it out one more time! 
		</div>
	</body>
</html>
~~~

## Columns

~~~
// columns0.html

<!DOCTYPE html>
<html lang="en">
	<head>
		<title>My Web Page</title>
	    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">
	    <style>
		    .row > div {
			    padding: 20px;
			    background-color: teal;
			    border: 2px solid black;
			    }
	    </style>
	</head>
	<body>
		<div class="container">
			<div class="row">
				<div class="col-3">
					This is a section.
				</div>
				<div class="col-3">
					This is another section.
				</div>
				<div class="col-3">
					This is a third section.
				</div>
				<div class="col-3">
					This is a fourth section.
				</div>
			</div>
		</div>
	</body>
</html>
~~~


~~~
// columns1.html

<!DOCTYPE html>
<html lang="en">
	<head>
		<title>My Web Page</title>
	    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">
	    <style>
		    .row > div {
			    padding: 20px;
			    background-color: teal;
			    border: 2px solid black;
			    }
	    </style>
	</head>
	<body>
		<div class="container">
			<div class="row">
				<div class="col-lg.3" col-sm-6" >
					This is a section.
				</div>
				<div class="col-lg.3" col-sm-6" >
					This is another section.
				</div>
				<div class="col-lg.3" col-sm-6" >
					This is a third section.
				</div>
				<div class="col-lg.3" col-sm-6" >
					This is a fourth section.
				</div>
			</div>
		</div>
	</body>
</html>
~~~

