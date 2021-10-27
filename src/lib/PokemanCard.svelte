<script>
	import { fade } from 'svelte/transition';
	export let pokeman;
</script>

<a href={`/pokemon/${pokeman.id}`} transition:fade sveltekit:noscroll>
	<img src={pokeman.image} alt={pokeman.name} />
	<h2>{pokeman.name}</h2>
</a>

<style lang="scss">
	a {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 6px;
		border-radius: 7px;
		background-color: lightgray;
		text-align: center;
		box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
		&:hover {
			box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
		}
	}
	h2 {
		text-transform: uppercase;
	}
	img {
		height: 8rem;
		width: 8rem;
	}
</style>
