<script>
    import {pokemon} from '../stores/pokestore.js'
</script>
<svelte:head>
    <title>Svelte Kit Pokedex</title>
</svelte:head>
<h1 class="text-4xl text-center my-8 uppercase">Sveltekit Pokedex</h1>
{#each $pokemon as pokeman}
    <p>{pokeman.name}</p>
{/each}
