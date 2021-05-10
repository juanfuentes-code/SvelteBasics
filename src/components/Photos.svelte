<script>
    import { onMount } from 'svelte';
    let photos = [];
    onMount(async () =>{
        console.log('onMount');
        const response = await fetch("https://jsonplaceholder.typicode.com/photos?_limit=20")
        photos = await response.json();
    });
</script>
<style>
    .Photos{
        width: 100%;
        display: grid;
        grid-template-columns: repeat(5,1fr);
        grid-gap:8px;
    }
</style>
<div class="Photos">
    {#each photos as photo}
    <figure>
        <img src={photo.thumbnailUrl} alt ={photo.title}>
        <ficaption>{photo.title}</ficaption>
    </figure>
    {:else}
    <p>Loading...</p>
    {/each}
</div>