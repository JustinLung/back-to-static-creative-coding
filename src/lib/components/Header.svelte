<script>
	let isActive = false;
	function toggleNavMenu() {
		isActive = !isActive;
		isActive ? document.body.classList.add('freeze') : document.body.classList.remove('freeze');
	}
	function closeNavMenu() {
		isActive = false;
		document.body.classList.remove('freeze');
	}
</script>

<header>
	<h1>Creative Coding</h1>
	<nav class:active={isActive}>
		<a href="/">Home</a>
		<a href="/">Projects</a>
		<a href="/">About</a>
		<a href="/">Contact</a>
	</nav>
	<div>
		<button on:click={toggleNavMenu} class:active={isActive}>
			<span />
			<span />
			<span />
		</button>
	</div>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		max-width: 80rem;
		margin: 0 auto;
	}
	nav {
		display: none;
	}
	nav a {
		position: relative;
		color: black;
		display: none;
	}
	nav a::before {
		content: '';
		position: absolute;
		bottom: -0.3rem;
		right: 0;
		width: 0;
		height: 2px;
		background-color: var(--color-dark);
		transition: width 1s cubic-bezier(0.25, 1, 0.5, 1);
		display: none;
		z-index: 30;
	}
	nav a:hover::before {
		left: 0;
		right: auto;
		width: 100%;
	}
	nav.active {
		position: fixed;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		font-size: 1.3rem;
		font-weight: bold;
		gap: 0.8rem;
		inset: 0;
		width: 100%;
		height: 100vh;
		background-color: var(--color-white);
		overflow: hidden;
		z-index: 20;
	}

	nav.active a {
		display: block;
	}

	div {
		background-color: #ffffff;
		padding: 1rem;
		border-radius: 50%;
		width: 3.5rem;
		height: 3.5rem;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	button {
		all: unset;
		display: block;
		position: relative;
		z-index: 1;
		cursor: pointer;
		z-index: 30;
	}
	button span {
		display: block;
		width: 2rem;
		height: 0.2rem;
		margin-bottom: 5px;
		position: relative;
		background-color: black;
		border-radius: 6px;
		transform-origin: 0 0;
		transition: 0.4s;
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
	@media (min-width: 60rem) {
		nav {
			display: flex;
			flex-direction: row;
			justify-content: center;
			align-items: center;
			gap: 1rem;
			position: relative;
			height: auto;
		}
		button {
			display: block;
		}
		nav a::before {
			display: block;
		}
	}
</style>
