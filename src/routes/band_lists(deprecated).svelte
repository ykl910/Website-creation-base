<script context='module'>
    import  supabaseClient  from '../../src/lib/supabase';
    export async function load({ fetch, session }) {
        const { data, error } = await supabaseClient
            .from('band')
            .select()
        console.log(data);
        return { props:{bands:data}, error };
        
    };
</script>

<script>
import { identity } from 'svelte/internal';

    export let bands;    
    export let id;
    export let name;
    export let type_of_music;
    export let type_of_event;
    export let short_description;
</script>


<h1>Available band</h1>

<div class="grid lg:grid-cols-3 gap-8"> 
    {#each bands as band}
        <div class="bg-white text-black p-6">
            <h2>{band.name}</h2>
            <p>{#if band.type_of_music}{band.type_of_music}{:else}<span class="text-gray-400">No specific type of music</span>{/if}</p>
            <p>{#if band.type_of_event}{band.type_of_event}{:else}<span class="text-gray-400">No specific type of event</span>{/if}</p>
            <p><a href="http://localhost:3000/band-{band.id}" class="text-blue-500">more details </a></p>
        </div>
    {/each}
    
</div>
