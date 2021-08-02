## Responsive Navigation Bar
Learn step by step how to create responsive navigation using HTML, CSS, and a little JavaScript.

> Resize the browser window to see how the responsive navigation menu work. [Link below ⬇]
> 
> [Live Demo](https://clickable-menu.netlify.app/)

 - [x] Step one [Add HTML]
 ```
<!--=-=-=-= Connect To Css =-=-=-=-->
<link rel="stylesheet" href="./assets/css/style.css">

<!--=-=-=-= Connect To Box Icon =-=-=-=-->
<link href='https://unpkg.com/boxicons@2.0.9/css/boxicons.min.css' rel='stylesheet'>

<nav class="nav" id="myNav">
	<a href="#home" class="active">Home</a>
	<a href="#news">News</a>
	<a href="#contact">Contact</a>
	<a href="#about">About</a>
	<a href="#" class="icon" onclick="clickableMenu()">
		<i class='bx bx-menu' ></i>
	</a>
</nav>
```
*The link with class="icon" is used to open and close the nav on small screens.*
 - [x] Step Two[Add CSS]
 ```
 /* =-= Navigation =-= */
 
 /* Add a black background color to the navigation */
.nav {
	overflow: hidden;
	background-color: var(--menu-color);
}

/* Style the links inside the navigation bar */
.nav a {
	float: left;
	display: block;
	color: var(--light-color);
	text-align: center;
	padding: .875rem 1rem;
}

/* Change the color of links on hover */
.nav a:hover {
	background-color:var(--hover-color);
	color: black;
}

/* Add an active class to highlight the current page */
.nav a.active {
	background-color: var(--active-color);
	color: white;
}

/* Hide the link that should open and close the topnav on small screens */
.nav a.icon {
	display: none;
}
 ```
  - [x] Step Three [Add Media Queries]
 
 ```
 /* When the screen is less than 600 pixels wide, hide all links, except for the first one ("Home"). Show the link that contains should open and close the nav (.icon) */
 @media screen and (max-width: 600px) {
	.nav a:not(:first-child) {
		display: none;
	}
	.nav a.icon {
		float: right;
		display: block;
	}
}

/* The "responsive" class is added to the topnav with JavaScript when the user clicks on the icon. This class makes the nav look good on small screens (display the links vertically instead of horizontally) */
@media screen and (max-width: 600px) {
	.nav.responsive {
		position: relative;
	}

	.nav.responsive .icon {
		position: absolute;
		right: 0;
		top: 0;
	}

	.nav.responsive a {
		float: none;
		display: block;
		text-align: left;
	}
}
 ```
 - [x] Step Four[Add JavaScript]
```
/* Toggle between adding and removing the "responsive" class to nav when the user clicks on the icon */
const clickableMenu = () => {
	let x = document.getElementById('myNav');
	if (x.className === 'nav') {
		x.className += ' responsive';
	} else {
		x.className = 'nav';
	}
}
``` 
Thank you 😊
