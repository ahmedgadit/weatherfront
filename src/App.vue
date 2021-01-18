<template>
	<div style="width:100%; height: 100%">
		<div class="header">
			<h1 style="color:white;">Wetter Online</h1>
		</div>
		<router-view/>
	</div>
</template>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}

#nav {
	padding: 30px;
}

#nav a {
	font-weight: bold;
	color: #2c3e50;
}

#nav a.router-link-exact-active {
	color: #42b983;
}
html, body{
	height: 100%;
}

* {
	box-sizing: border-box;
}

body {
	font-family: Arial, Helvetica, sans-serif;
}

/* Float four columns side by side */
.column {
	float: left;
	width: 30%;
	padding: 4px 4px;
}

.column-half {
	float: left;
	width: 50%;
	padding: 4px 4px;
}

/* Remove extra left and right margins, due to padding */
.row {margin: 0 -5px;}

/* Clear floats after the columns */
.row:after {
	content: "";
	display: table;
	clear: both;
}

/* Responsive columns */
@media screen and (max-width: 600px) {
	.column {
		width: 100%;
		display: block;
		margin-bottom: 20px;
	}
}

/* Style the counter cards */
.card {
	box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
	padding: 35px;
	text-align: center;
	background-color: white;
}
.a-div{
	display:block;
	height:100%;
	width:100%;
}
.box{
	background-color: #f2f2f2 ;
	padding: 2%;
}
.header{
	min-height: 10%;
	padding: 1px;
	background-color: black;
	font-family: -webkit-body;
}
.text{
	text-align: left;
}
</style>
