<script lang="ts">
	import { onMount } from 'svelte';

	onMount(() => {
		let circle = document.querySelector('.cursor');
		let container = document.querySelector('.navigation');
		container?.addEventListener('mousemove', (a) => {
			// @ts-ignore
			circle.style.top = a.clientY + 'px';
			// @ts-ignore
			circle.style.left = a.clientX + 'px';
		});
	});
</script>

<section>
	<nav class="navigation">
		<a href="/"><span>Home</span></a>
		<a href="/about"><span>Our Story</span></a>
		<a href="/"><span>Studio</span></a>
		<a href="/"><span>Contact</span></a>
		<div class="cursor">
			<svg viewBox="0 0 100 100" width="100" height="100">
				<defs>
					<path
						id="circle"
						d="
                      M 50, 50
                      m -37, 0
                      a 37,37 0 1,1 74,0
                      a 37,37 0 1,1 -74,0"
					/>
				</defs>
				<text font-size="17">
					<textPath xlink:href="#circle"> BIZZARE PUNK </textPath>
				</text>
			</svg>
		</div>
	</nav>
</section>

<style>
	svg {
		fill: currentColor;
		height: auto;
		transform-origin: center;
		width: 100%;
		animation: rotation 2s ease-in-out infinite;
	}

	@keyframes rotation {
		0% {
			transform: rotate(360deg);
		}
		100% {
            transform: rotate(0deg);
        }
	}

	nav {
		height: 100vh;
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		gap: 2rem;
		position: relative;
	}

	a {
		font-size: 2.5rem;
		text-decoration: none;
		text-transform: uppercase;
		font-weight: 900;
	}

	a:hover ~ .cursor {
		width: 20rem;
		height: 20rem;
		background-color: red;
        transition: .3s ease-in-out;
	}

	.cursor {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		width: 5rem;
		height: 5rem;
		background-color: var(--color-white);
		border-radius: 50%;
		mix-blend-mode: difference;
		cursor: pointer;
		z-index: -1;
		padding: 1rem;
	}
</style>
