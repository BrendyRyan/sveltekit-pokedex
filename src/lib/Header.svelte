<script>
	import { page } from '$app/stores';

	const id = Math.floor(Math.random() * 151) + 1;

	const routes = [
		{ href: '/', name: 'Home' },
		{ href: '/about', name: 'About Me' },
		{ href: `/pokemon/${id}`, name: 'Pokemon' }
	];
</script>

<header>
	<nav>
		<ul>
			{#each routes as route}
				<li class:active={route.href === $page.path}>
					<a href={route.href}>{route.name}</a>
				</li>
			{/each}
		</ul>
	</nav>
</header>

<style lang="scss">
	nav {
		border-bottom: 2px solid #000;
	}
	ul {
		display: flex;
		justify-content: center;
	}
	li {
		margin: 1rem;
		&.active {
			text-decoration: underline;
		}
		&:hover {
			color: red;
		}
	}
</style>
