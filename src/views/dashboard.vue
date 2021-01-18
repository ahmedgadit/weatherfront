<template>
	<div class="box">
		<p class="text">Dashboard</p>
		<div class="row">
			<template>
				<weather-card :weather="weather"></weather-card>
			</template>
			<div class="column">
				<router-link :tag="anchor" :to="{ name: 'Weatherdetail', params: {'city':'keil'} }" ></router-link>
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
export default{
	data(){
		return{
			weather: [],
		}
	}
}
</script>
