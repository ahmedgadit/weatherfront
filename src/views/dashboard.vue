<template>
	<div class="box">
		<p class="text">Dashboard</p>
		<div class="row">
			<template>
				<weather-card :weather="weather"></weather-card>
			</template>
			<div class="column">
				<router-link  :to="{ name: 'Weatherdetail', params: {'city':'keil'} }"></router-link>
				<div class="card">
					<div>
						{{ weather.city }}
					</div>
					<div class="row">
						<div>
							<h3>Add</h3>
						</div>
					</div>
				</div>
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
			weather: [],
		}
	},
	Components: {
		WeatherCard,
	},
	mounted(){
		axios.get('http://localhost:5000/api/weather/city')
		.then(response => {
			console.log(response.data.user);
		})
		.catch(error => {
			console.log(error.response.data);
		});
	}
}
</script>
