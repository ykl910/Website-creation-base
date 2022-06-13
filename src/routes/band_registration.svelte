


<script>
    import  supabaseClient  from '../../src/lib/supabase';
	import MultiSelect from './MultiSelect.svelte';

    let name, type_of_music, mobile_number, email, number_of_members, website, short_description, type_of_event, price, picture_url, video_url;
    const sendData = async () => {
        const { data, error } = await supabaseClient
            .from('band')
            .insert({ name, type_of_music, mobile_number, email, number_of_members, website, type_of_event, short_description,  price, picture_url, video_url })

        return { data, error };
    };
</script>

<h1>Register your band and wait to be contacted!</h1>
<img src="static/registration.jpg" alt="band">

<form action="" on:submit|preventDefault={sendData}>
    <div class="container">
        <label for="name">Name</label>
        <input type="text" bind:value={name} />
    </div>
    <div class="container">
        <label for="type_of_music">Type of music</label>
        <input type="text" bind:value={type_of_music} />
    </div>
    <div class="container">
        <label for="mobile">Mobile</label>
        <input type="text" bind:value={mobile_number} />
    </div>
    <!-- <div class="container"> -->
        <label for="email">Email</label>
        <input type="text" bind:value={email} />
    <!--</div>-->
    <div class="container">
        <label for="number_of_members">Number of members</label>
        <input type="text" bind:value={number_of_members} />
    </div>
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
        <label for="website">Website</label>
        <input type="text" bind:value={website} />
    </div>
    <div class="container">
        <label for="price">Price</label>
        <input type="text" bind:value={price} />
    </div>
    <div class="container">
        <label for="picture_url">Picture</label>
        <input type="text" bind:value={picture_url} />
    </div>
    <div class="container">
        <label for="video_url">Video</label>
        <input type="text" bind:value={video_url} />
    </div>
    <div class="container">
        <label for="short_description">Short description</label>
        <input type="text" bind:value={short_description} />
    </div>

    <button type="submit">Send</button>
</form>