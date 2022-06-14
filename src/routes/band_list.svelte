<script context='module'>
	import MultiSelect from './MultiSelect.svelte';
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
	export async function search() {
		console.log(type_of_event);
		console.log(type_of_music);
		const { data, error } = await supabaseClient
			.from('band')
			.select()
			.filter('type_of_music','in',`(${type_of_music})`)
			.contains('type_of_event',`{${type_of_event}}`)
		console.log(error);
		search_results = data;
    };

	export let search_results = [ ];
	export let bands;    
	let type_of_music;
	let type_of_event;

	function hide(){
		var i = document.getElementById("initial");
		i.style.display = "none";
  	}
</script>


<div class="container z-50">
	<label for="type_of_event">Type of event</label>
	<MultiSelect bind:value={type_of_event}>
		<option value="company_events"><span class = "text-black" >Company events</span></option>
		<option value="weddings">Weddings</option>
		<option value="restaurants">Restaurants</option>
		<option value="bars">Bars</option>
		<option value="private_beaches">Private beaches</option>
	</MultiSelect>
</div>
<div class="container z-10">
	<label for="type_of_music">Type of music</label>
	<MultiSelect bind:value={type_of_music}>
	  <option value="hiphop" class="z-10">Hiphop</option>
	  <option value="jazz">Jazz</option>
	  <option value="rock">Rock</option>
	  <option value="classical">Classical</option>
	  <option value="electronic">Electronic</option>
	  <option value="country">Counry</option>
	</MultiSelect>

	<button on:click={search} on:click={hide}>Search</button>
</div>



<div class="grid lg:grid-cols-3 gap-8"> 
    {#each search_results as band}
        <div class="bg-white text-black p-6">
            <h2>{band.name}</h2>
            <p>{#if band.type_of_music}{band.type_of_music}{:else}<span class="text-gray-400">No specific type of music</span>{/if}</p>
            <p>{#if band.type_of_event}{band.type_of_event}{:else}<span class="text-gray-400">No specific type of event</span>{/if}</p>
            <p><a href="http://localhost:3000/band-{band.id}" class="text-blue-500">more details </a></p>
        </div>
    {/each}
    
</div>

<div class="grid lg:grid-cols-3 gap-8" id="initial"> 
    {#each bands as band}
        <div class="bg-white text-black p-6">
            <h2>{band.name}</h2>
            <p>{#if band.type_of_music}{band.type_of_music}{:else}<span class="text-gray-400">No specific type of music</span>{/if}</p>
            <p>{#if band.type_of_event}{band.type_of_event}{:else}<span class="text-gray-400">No specific type of event</span>{/if}</p>
            <p><a href="http://localhost:3000/band-{band.id}" class="text-blue-500">more details </a></p>
        </div>
    {/each}
</div>