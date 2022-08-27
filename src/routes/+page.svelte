<script>
import Pokecard from "../components/pokecard.svelte";
import {pokemon} from "../stores/pokestore.js"    
let searchTerm = "";
let filterpoke = [];

$:{
    if(searchTerm){
        filterpoke = $pokemon.filter(pokeman => pokeman.name.toLowerCase().includes(searchTerm.toLowerCase()));
    }else{
        filterpoke = [...$pokemon]
    }
}

</script>
<svelte:head>
    <title>Svelte Pokedex</title>
</svelte:head>

<h1 class="text-4xl text-center my-8 uppercase">Svelte Pokedex</h1>
<input type="text" class="w-full rounded-md mb-4 text-lg p-4 border-2 border-gray-200" bind:value={searchTerm} placeholder = "Search Pokemon">
<div class="grid gap-4 md:grid-cols-2 grids-cols-1">
    {#each filterpoke as pokeman}
    <Pokecard pokeman={pokeman}/>
    {/each}
</div>

 


