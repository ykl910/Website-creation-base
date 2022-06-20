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
		var j = document.getElementById("show");
		j.style.display = "block";
  	}
</script>

<style> 
	.band {
		background-color: white;
		color: black;
		padding: 18px;
		border-radius: 10px;
		transition: all .2s;
		}
	.band:hover {
	  transform: scale(1.05);
	}
</style>

<div class="grid lg:grid-cols-2 gap-6">
	<div class="container z-50">
		<label for="type_of_event">Type of event</label>
		<MultiSelect bind:value={type_of_event}>
			<option value="company_events">Company events</option>
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
		<option value="country">Country</option>
		</MultiSelect>

	</div>
</div>
<button on:click={search} on:click={hide}>Search</button>

<div id="show" style="display:none">
	<h2>Search results</h2>
	{#if type_of_music==""}
	<p>Please select at least one type of music</p>{/if}
	{#if search_results==""}<p>No band available</p>{/if}
</div>
<div class="grid lg:grid-cols-3 gap-8"> 
	{#each search_results as band}
        <div class="band">
            <h2>{band.name}</h2>
            <p>{#if band.type_of_music}{band.type_of_music}{:else}<span class="text-gray-400">No specific type of music</span>{/if}</p>
            <p>{#if band.type_of_event}{band.type_of_event}{:else}<span class="text-gray-400">No specific type of event</span>{/if}</p>
            <p><a href="http://localhost:3000/band-{band.id}" class="text-blue-500" target="_blank">more details </a></p>
        </div>
{/each}
</div>

<div id="initial">
<h2>All bands</h2>
<div class="grid lg:grid-cols-3 gap-8"> 
	{#each bands as band}
        <div class="band">
            <h2>{band.name}</h2>
            <p>{#if band.type_of_music}{band.type_of_music}{:else}<span class="text-gray-400">No specific type of music</span>{/if}</p>
            <p>{#if band.type_of_event}{band.type_of_event}{:else}<span class="text-gray-400">No specific type of event</span>{/if}</p>
            <p><a href="http://localhost:3000/band-{band.id}" class="text-blue-500">more details </a></p>
        </div>
    {/each}
</div>
</div>