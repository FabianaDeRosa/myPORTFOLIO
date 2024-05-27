<script>
    import SingleWork from "./SingleWork.svelte";
    import works from "$lib/JSON/works.json";
    import { page } from "$app/stores";

    const work = works[$page.params.item];
</script>


<svelte:head>
    <title>Works - {work.title}</title>
    <meta name="Portfolio" content="My portfolio works">
</svelte:head>




<div id="single-item-wrapper">

    <SingleWork {...work} />

</div>
