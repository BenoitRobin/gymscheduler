<!-- Mon script -->

<script>
	import TrainingDay from './components/TrainingDay.svelte';

	export let name;
</script>

<!-- Mon style -->

<style type="text/scss">
.container {
	text-align: center;
	padding: 1em;
	margin: 0 auto;

	&-mainTitle {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
}
</style>
	
<!-- Mon code -->

<main class="container">
	<h1 class="container-mainTitle">{name}</h1>

	<TrainingDay />
</main>