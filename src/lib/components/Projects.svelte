<script lang="ts">
	import gsap from 'gsap';
	import { onMount } from 'svelte';

	onMount(() => {
		gsap.to(
            "img", 
            {opacity: 1, stagger: 0.15, y: 0, delay: 0.4}
		);
	});
</script>

<section>
	<div>
		<h2>Projects</h2>
		<p>
			Lorem ipsum dolor, sit amet consectetur adipisicing elit. Facere expedita nesciunt, minima
			nobis labore maiores iure cumque deserunt quas quos obcaecati! Incidunt aut dolores ducimus
			cupiditate illo aliquam, modi aliquid!
		</p>
	</div>
	<div>
		<img src="https://source.unsplash.com/random" alt="Project" />
		<img src="https://source.unsplash.com/random" alt="Project" />
		<img src="https://source.unsplash.com/random" alt="Project" />
		<img src="https://source.unsplash.com/random" alt="Project" />
		<img src="https://source.unsplash.com/random" alt="Project" />
		<img src="https://source.unsplash.com/random" alt="Project" />
	</div>
</section>

<style>
	section {
		padding: 1rem;
		max-width: 55rem;
		margin: 0 auto;
	}
	div:first-child {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		gap: 1.5rem;
		margin: 4rem 0;
	}

	h2 {
		font-size: 3.5rem;
	}

	p {
		font-size: 1.2rem;
		line-height: 1.5rem;
	}

	div:last-child {
		max-width: 55rem;
		margin: 0 auto;
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 1rem;
	}

	img {
		border-radius: 0.5rem;
		max-width: 30rem;
		width: 100%;
        transform: translateY(20px);
        opacity: 0;
	}

	@media (max-width: 55rem) {
		h2 {
			margin: 0;
		}
		div:first-child {
			margin: 0;
			gap: 0;
			align-items: flex-start;
			flex-direction: column;
		}
		div:last-child {
			grid-template-columns: 1fr;
		}

		img {
			max-width: 100%;
		}
	}
</style>
