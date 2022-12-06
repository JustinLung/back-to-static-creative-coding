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
		max-width: 80rem;
		margin: 0 auto;
		padding: 1rem;
	}
</style>
