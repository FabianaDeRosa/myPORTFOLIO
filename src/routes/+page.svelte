<svelte:head>
    <title>Fabiana De Rosa</title>
    <meta name="Portfolio" content="UX/UI front-end portfolio">
</svelte:head>

<script>
    import works from "$lib/JSON/works.json"
	import Works from "./Works.svelte";
</script>



<section>
    {#each works as work}
        <Works {...work} />
     {/each}
</section>


<style lang="scss">

    :global(main){
        display: grid;
    }

    section{
        display: grid;
        grid-template-columns: repeat( auto-fit, minmax(20em, 1fr) );
    }

    @media screen and (max-width: 600px) {

        section{
        display: grid;
        grid-template-columns: 1fr;
        width: 35rem;
    }

}  

</style>