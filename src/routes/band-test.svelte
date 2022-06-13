<script context='module'>
	import MultiSelect from './MultiSelect.svelte';
    import  supabaseClient  from '../../src/lib/supabase';

	
	
</script>

<script>

	export async function search() {
		console.log(type_of_music);
		const { data, error } = await supabaseClient
			.from('band')
			.select()
			.in('type_of_music', type_of_music)
		console.log(data);
			
		search_results = data;
    };

	export let search_results = [ ];
	export let bands;    
	export let id;
	export let name;
	//export let type_of_music;
	export let type_of_event;
	export let short_description;
	let type_of_music;
</script>

<div class="container">
	<label for="type_of_event">Type of event</label>
	<MultiSelect bind:value={type_of_event}>
	  <option value="company_event"><span class = "text-black" >Company events</span></option>
	  <option value="wedding">Weddings</option>
	  <option value="Restaurants">Restaurants</option>
	  <option value="Bars">Bars</option>
	  <option value="Private_beaches">Private beaches</option>
	</MultiSelect>
</div>
<div class="container">
	<label for="type_of_music">Type of music</label>
	<MultiSelect bind:value={type_of_music}>
	  <option value="hiphop">Hiphop</option>
	  <option value="jazz">Jazz</option>
	  <option value="Rock">Rock</option>
	  <option value="Classical">Classical</option>
	  <option value="Electronic">Electronic</option>
	  <option value="Country">Counry</option>
	</MultiSelect>

	<button on:click={search}>button</button>
</div>



<div class="grid lg:grid-cols-3 gap-8"> 
    {#each search_results as band}
        <div class="bg-white text-black p-6">
            <h2>{band.name}</h2>
            <p>{#if band.type_of_music}{band.type_of_music}{:else}<span class="text-gray-400">No specific type of music</span>{/if}</p>
            <p>{#if band.type_of_event}{band.type_of_event}{:else}<span class="text-gray-400">No specific type of event</span>{/if}</p>
            <p><a href="http://localhost:3000/band-{band.id}" class="text-blue-500">show detial </a></p>
        </div>
    {/each}
    
</div>