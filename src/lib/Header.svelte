<script>
	import { page } from '$app/stores';

	const routes = [
		{ href: '/', name: 'Home' },
		{ href: '/about', name: 'About Me' },
		{ href: '/contact', name: 'Pokemon' }
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
		height: 4rem;
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
