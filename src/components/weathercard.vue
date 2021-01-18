<template>
	<div class="column">
		<div class="card">
			<div>
				{{ weather.city }}
			</div>
			<div class="row">
				<<router-link :to="{ name: 'Weatherdetail', params: {'city':'keil'} }" class="a-div"></router-link>
				<div class="column-half">
					<img />
				</div>
				<div class="column-half">
					<p>Montag. 01.10.18</p>
					<p>4C/14C</p>
				</div>
			</div>
		</div>
	</div>
</template>
