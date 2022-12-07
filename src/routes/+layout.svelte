<script lang="ts">
	import Header from '$lib/components/Header.svelte';
	import '../styles/global.css';
	import '../styles/theme.css';
</script>

<Header />
<main>
	<slot />
</main>

<style>
	main {
		padding: 1rem 3rem;
	}

	@media (max-width: 55rem) {
		main {
			padding: 1rem;
		}
	}
</style>
