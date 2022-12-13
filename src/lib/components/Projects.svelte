<script lang="ts">
	import { gsap } from 'gsap/dist/gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';
	import { onMount } from 'svelte';

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);

		ScrollTrigger.batch('.project', {
            interval: 0.1,
            start: "top center",
			onEnter: (batch) =>
				gsap.to(batch, { autoAlpha: 1, stagger: 0.15, opacity: 1, y: 0})
		});
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
		<img src="profile.JPG" alt="Project" class="project" />
		<img src="profile.JPG" alt="Project" class="project" />
		<img src="profile.JPG" alt="Project" class="project" />
		<img src="profile.JPG" alt="Project" class="project" />
		<img src="profile.JPG" alt="Project" class="project" />
		<img src="profile.JPG" alt="Project" class="project" />
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

	.project {
		border-radius: 0.5rem;
		max-width: 30rem;
		width: 100%;
		transform: translateY(20px);
		opacity: 0;
	}

	@media (max-width: 55rem) {
		h2 {
			font-size: 2.5rem;
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
