<script lang="ts">
	import gsap from 'gsap';
	let isActive = false;

	function toggleNavMenu() {
		isActive = !isActive;
		if (isActive) {
			gsap.to('li', { duration: 0.5, opacity: 1, stagger: 0.15, y: 0, delay: 0.4 });
		} else {
			gsap.set('li', { opacity: 0, y: 20, delay: 0.5 });
		}
	}
</script>

<header>
	<h1>Creative Coding</h1>
	<nav class:active={isActive}>
		<ul>
			<li><a href="/">Home</a></li>
			<li><a href="/">Projects</a></li>
			<li><a href="/">About</a></li>
			<li><a href="/">Contact</a></li>
		</ul>
		<span />
		<ul>
			<li><a href="/">FAQ</a></li>
			<li><a href="/">TERMS OF SERVICE</a></li>
		</ul>
	</nav>
	<button on:click={toggleNavMenu} class:active={isActive}>
		<span />
		<span />
		<span />
	</button>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1rem;
		position: relative;
	}
	h1 {
		color: var(--color-white);
		mix-blend-mode: difference;
		z-index: 22;
	}

	span {
		width: 90%;
		height: 2px;
		background-color: var(--color-dark);
	}

	nav {
		clip-path: circle(30px at calc(100% - 15px - 1rem) calc(40px + 1rem));
		transition: 0.5s clip-path ease-in-out;
		width: 100%;
		height: 100vh;
		position: absolute;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		font-size: 1.3rem;
		font-weight: bold;
		inset: 0;
		background-color: var(--color-white);
		overflow: hidden;
		z-index: 20;
		transition: 0.5s clip-path ease-in-out;
	}

	ul {
		width: 100%;
		max-width: 30rem;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		justify-content: center;
		list-style: none;
		color: var(--color-dark);
		font-size: 3rem;
		gap: 1rem;
		margin-bottom: 1rem;
	}

	ul:last-child {
		margin-top: 1rem;
		gap: 0;
		font-size: 2rem;
	}

	li {
		text-decoration: none;
		opacity: 0;
		transform: translateY(20px);
	}

	nav a {
		position: relative;
		color: var(--color-dark);
		text-decoration: none;
	}

	nav a::before {
		content: '';
		position: absolute;
		bottom: -0.3rem;
		right: 0;
		width: 0;
		height: 0.2rem;
		background-color: var(--color-dark);
		transition: width 0.5s cubic-bezier(0.25, 1, 0.5, 1);
		display: none;
		z-index: 30;
	}
	nav a:hover::before {
		left: 0;
		right: auto;
		width: 100%;
	}

	nav.active {
		clip-path: circle(100%);
	}

	button {
		all: unset;
		display: block;
		position: relative;
		z-index: 1;
		cursor: pointer;
		z-index: 30;
	}

	button::after {
		content: "MENU";
		color:var(--color-white); 
		position: absolute;
		top: 2.7rem;
		left: 50%;
		transform: translate(-50%);
		mix-blend-mode: difference;
	}

	button span {
		display: block;
		width: 2rem;
		height: 0.2rem;
		margin-bottom: 5px;
		position: relative;
		background-color: var(--color-dark);
		border-radius: 6px;
		transform-origin: 0 0;
		transition: 0.3s;
	}
	button span:last-child {
		margin: 0;
	}

	button.active span:nth-child(1) {
		transform: translate(0px, -2px) rotate(45deg);
	}

	button.active span:nth-child(2) {
		opacity: 0;
		transform: translateX(15px);
	}

	button.active span:nth-child(3) {
		transform: translate(-3px, 3px) rotate(-45deg);
	}

	button:not(.active):hover span:nth-child(2) {
		width: 1.7rem;
	}

	button:not(.active):hover span:nth-child(1) {
		width: 1.2rem;
	}

	@media (min-width: 60rem) {
		header {
			padding: 1rem 3rem;
		}

		nav {
			clip-path: circle(30px at calc(100% - 15px - 3rem) calc(40px + 1rem));
			gap: 0.8rem;
			flex-direction: row;
		}
		span {
			height: 80%;
			width: 2px;
			background-color: var(--color-dark);
		}
		button {
			display: block;
		}

		ul {
			height: 100vh;
		}

		ul:last-child {
			gap: 0.8rem;
			font-size: 2rem;
		}

		nav a::before {
			display: block;
		}
	}
</style>
