<template>
	<div class="box">
		<p class="text">Dashboard</p>
		<div class="row">
			<template v-for="(weather, index) in fav_weather" :key="index" >
				<weather-card  :weather="weather" ></weather-card>
			</template>
			<div class="column">
				<a>
					<div class="card">
						<div>
						</div>
						<div class="row">
							<div>
								<button @click="openCity"> Add </button>
							</div>
						</div>
					</div>
				</a>
			</div>
		</div>

		<div id="myModal" class="modal">

			<!-- Modal content -->
			<div class="modal-content">
				<span @click="closeModal" class="close">&times;</span>
				<label class="typo__label">select your favourity City</label>
				<select v-model="selected">
					<option v-for="(weather, index) in weathers" :value="weather" :key="index">{{ weather.city }}</option>
				</select>
				<button @click="addFavWeather">Add</button>
			</div>

		</div>
	</div>
</template>
<script>
import WeatherCard from "../components/weathercard"
import axios from 'axios';
export default{
	data(){
		return{
			selected:{},
			weathers: [],
			fav_weather: [],
		}
	},
	components: {
		WeatherCard,
	},
	mounted(){
		axios.get('http://127.0.0.1:5000/api/weather')
		.then(response => {
			this.weathers = response.data.data;
			console.log(response.data.data);
			console.log(this.weathers);
		})
		.catch(error => {
			console.log(error.response.data);
		});
	},
	methods: {
		openCity(){
			var modal = document.getElementById("myModal");
			modal.style.display = "block";
		},
		closeModal(){
			var modal = document.getElementById("myModal");
			modal.style.display = "none";
		},
		addFavWeather(){
			var self = this ;
			let checkCond = this.fav_weather.findIndex(element => element.id === self.selected.id);
			if (checkCond < 0) {
				this.fav_weather.push(self.selected);
			}
		}
	},
}
</script>
<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>
<style>
.modal {
	display: none; /* Hidden by default */
	position: fixed; /* Stay in place */
	z-index: 1; /* Sit on top */
	left: 0;
	top: 0;
	width: 100%; /* Full width */
	height: 100%; /* Full height */
	overflow: auto; /* Enable scroll if needed */
	background-color: rgb(0,0,0); /* Fallback color */
	background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

/* Modal Content/Box */
.modal-content {
	background-color: #fefefe;
	margin: 15% auto; /* 15% from the top and centered */
	padding: 20px;
	border: 1px solid #888;
	width: 80%; /* Could be more or less, depending on screen size */
}

/* The Close Button */
.close {
	color: #aaa;
	float: right;
	font-size: 28px;
	font-weight: bold;
}

.close:hover,
.close:focus {
	color: black;
	text-decoration: none;
	cursor: pointer;
}

</style>
