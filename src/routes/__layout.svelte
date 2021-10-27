<script>
	import '../../styles/normalize.css';
	import '../../styles/reset.css';

	import Footer from '$lib/Footer.svelte';
	import Header from '$lib/Header.svelte';
</script>

<div class="container">
	<Header />
	<main><slot /></main>
	<Footer />
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
		height: 100vh;
	}
	main {
		flex-grow: 1;
		padding: 2rem;
	}
</style>
