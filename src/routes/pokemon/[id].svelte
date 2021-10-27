<script context="module">
	export async function load({ page }) {
		const id = page.params.id;
		const url = `https://pokeapi.co/api/v2/pokemon/${id}`;
		const res = await fetch(url);
		const pokeman = await res.json();
		return { props: { pokeman } };
	}
</script>

<script>
	export let pokeman;
	const type = pokeman.types[0].type.name;
</script>

<div class="pokemon">
	<h1>{pokeman.name}</h1>
	<p>
		Type: <strong>{type}</strong> | Height: <strong>{pokeman.height}</strong> | Weight:
		<strong>{pokeman.weight}</strong>
	</p>
	<img src={pokeman.sprites['front_default']} alt={pokeman.name} />
</div>

<style lang="scss">
	h1 {
		font-size: 1.5rem;
		text-align: center;
		margin-bottom: 2rem;
		text-transform: uppercase;
	}
	.pokemon {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	img {
		height: 8rem;
		width: 8rem;
	}
</style>
