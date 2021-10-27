<script>
	import { pokemon } from './stores/pokemon.json';
	import PokemanCard from '$lib/PokemanCard.svelte';

	let searchTerm = '';
	let filteredPokemon = [];

	//$: means reactivity, like UseEffect in React
	$: {
		console.log(searchTerm);
		if (searchTerm) {
			//filter pokemon
			filteredPokemon = $pokemon.filter((pokeman) =>
				pokeman.name.toLowerCase().includes(searchTerm.toLowerCase())
			);
		} else {
			filteredPokemon = [...$pokemon];
		}
	}
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<h1>SvelteKit Pokedex</h1>

<input type="text" placeholder="Search Pokemon" bind:value={searchTerm} />

<div class="pokecard">
	{#each filteredPokemon as pokeman}
		<PokemanCard {pokeman} />
	{/each}
</div>

<style lang="scss">
	h1 {
		text-align: center;
	}
	.pokecard {
		display: grid;
		gap: 1rem;
		grid-template-columns: 1fr 1fr 1fr;
		margin: 10px 0px 10px 0px;
	}
	input {
		width: 100%;
		border-radius: 7px;
		padding: 0.1rem;
		margin-top: 1rem;
		font-size: 1.3rem;
		&:focus {
			border-color: blue;
		}
	}
</style>
