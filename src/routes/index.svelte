<script>
	import { pokemon } from './api/pokemon.json';
	console.log($pokemon);
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<h1>SvelteKit Pokedex</h1>

{#each $pokemon as pokeman}
	<p>{pokeman.name}</p>
{/each}

<style lang="scss">
	h1 {
		text-align: center;
	}
</style>
