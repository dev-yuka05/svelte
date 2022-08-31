<script>
	export let name;
	import Home from './home.svelte';
	import Count from './count.svelte';
	import Router from 'svelte-spa-router';
	const routes = {
		'/': Home,
		'/count': Count
	};
</script>

<main>
	<div>
		<a href="#/">home</a>
		<a href="#/count">count</a>
	</div>

	<Router {routes} />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>