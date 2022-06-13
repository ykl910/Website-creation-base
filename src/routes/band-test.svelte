<script>

	import MultiSelect from './MultiSelect.svelte';
	let type_of_event = []
	let type_of_music = []

</script>

<div class="container">
	<label for="type_of_event">Type of event</label>
	<MultiSelect bind:value={type_of_event}>
	  <option value="Company_events"><span class = "text-black" >Company events</span></option>
	  <option value="Weddings">Weddings</option>
	  <option value="Restaurants">Restaurants</option>
	  <option value="Bars">Bars</option>
	  <option value="Private_beaches">Private beaches</option>
	</MultiSelect>
</div>
<div class="container">
	<label for="type_of_music">Type of music</label>
	<MultiSelect bind:value={type_of_music}>
	  <option value="Hiphop">Hiphop</option>
	  <option value="Jazz">Jazz</option>
	  <option value="Rock">Rock</option>
	  <option value="Classical">Classical</option>
	  <option value="Electronic">Electronic</option>
	  <option value="Country">Counry</option>
	</MultiSelect>
</div>