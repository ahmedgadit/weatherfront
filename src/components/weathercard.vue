<template>
	<div class="column">
		<div class="card">
			<router-link :to="{ name: 'Weatherdetail', params: {'city':weather.id} }" style="text-decoration: none">
				<div>
					{{ weather.city }}
				</div>
				<div class="row">
					<div class="column-half">
						<img style="float:left;width: 150px;margin-top: 15px;" alt="scattered clouds" src="03n@2x.png" height="120" width="120">
					</div>
					<div class="column-half">
						<p style="text-align: left;">Montag. 01.10.18</p>
						<p style="text-align: left;">
							Bewolkt<br>
							4C/14C<br>
							20% Regen
						</p>
					</div>
				</div>
			</router-link>
		</div>
	</div>
</template>
<script>
	export default {
		props: ['weather'],
		methods: {
			bringIcon (icon){
				return 'http://openweathermap.org/img/wn/' + icon + '@2x.png';
			}
		},
	}
</script>
