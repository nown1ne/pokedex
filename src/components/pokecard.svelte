<script>
    export let pokeman;
import { transition_in } from 'svelte/internal';
    import {fade} from 'svelte/transition';
</script>
<a class="p-6 bg-gray-100 text-gray-800 text-center rounded-md shasow-sm hover:shadow-md flex flex-col items-center" href={`/pokemon/${pokeman.id}`} transition:fade>
    <img class="h-40 w-40" src={pokeman.image} alt={pokeman.name}>
    <h2 class="uppercase text-2xl" >{pokeman.id}. {pokeman.name}</h2>
</a>