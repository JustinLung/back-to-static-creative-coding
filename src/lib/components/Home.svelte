<section id="home">
	<h2>Hi, Welcome to this site!</h2>
	<p>
		Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam dolore quis ullam aliquid ut
		dolorem voluptates quisquam animi quibusdam labore totam non id, similique tempore, odio
		consectetur nihil temporibus obcaecati!
	</p>
</section>

<style>
	section {
		height: 30rem;
		display: flex;
		flex-direction: column;
		justify-content: center;
		background-color: var(--color-wine);
		padding: 1rem 3rem;
	}
	h2 {
		font-size: 3rem;
		margin: 0;
	}
	p {
		margin: 0;
		max-width: 30rem;
		font-size: 1.2rem;
		line-height: 1.5rem;
	}

	@media (max-width: 55rem) {
		section {
			padding: 1rem;
		}
	}
</style>
