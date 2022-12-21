<script lang="ts">
    import PageTransition from '$lib/components/PageTransition.svelte'
</script>

<PageTransition/>
    <section>
        <h2>Our story</h2>
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolor modi ducimus praesentium laboriosam commodi magni illum temporibus earum itaque voluptatem laudantium, unde quis necessitatibus, impedit fuga. Vitae debitis itaque ratione!</p>
    </section>


<style>
    section {
        max-width: 70rem;
        margin: 0 auto;
        height: 30rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    h2, p {
        margin: 0;
        max-width: 30rem;
    }

    h2 {
        font-size: 3rem;
    }

    p {
        font-size: 1.2rem;
        line-height: 2rem;
    }
</style>

