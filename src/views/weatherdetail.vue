<template>
	<div class="box">
		<p class="text">Dashboard</p>
		<div class="row">
			<div class="column">
				<div class="card">
					<div>
						Darmstadt
					</div>
					<div class="row">
						<div class="column-half">
							<template>
								<img style="float:left;width: 150px;margin-top: 15px;" alt="scattered clouds" :src="bringIcon('10d')" height="120" width="120">
							</template>
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
				</div>
			</div>

			<div class="column">
				<div class="card">
					<h3>Card 2</h3>
					<p>Some text</p>
					<p>Some text</p>
				</div>
			</div>

			<div class="column">
				<div class="card">
					<h3>Card 3</h3>
					<p>Some text</p>
					<p>Some text</p>
				</div>
			</div>

			<div class="column">
				<div class="card">
					<h3>Card 4</h3>
					<p>Some text</p>
					<p>Some text</p>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
export default{

	methods: {
			bringIcon (icon){
				return 'http://openweathermap.org/img/wn/' + icon + '@2x.png';
			}
	}
}
</script>
