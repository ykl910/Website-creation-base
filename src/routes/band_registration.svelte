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

    function submitted() {
        alert('Submitted!')
    }
</script>


<style>
    img { 
        object-fit: cover;
        height: 400px;
        width: 100%;
        overflow: hidden;
    }
</style>

<h1>Register your band and wait to be contacted!</h1>
<br>
<img src="static/registration.jpg" alt="band">
<form action="" on:submit|preventDefault={sendData}>
    <div class="mb-12">
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="name">Name</label></div>
            <div class="basis-3/4"><input type="text" bind:value={name} /></div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="type_of_music">Type of music</label></div>
            <div class="basis-3/4"><input type="text" bind:value={type_of_music} /></div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="mobile">Mobile</label></div>
            <div class="basis-3/4"><input type="text" bind:value={mobile_number} /></div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="email">Email</label></div>
            <div class="basis-3/4"><input type="text" bind:value={email} /></div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="type_of_event">Type of event</label></div>
            <div class="basis-3/4">
                <MultiSelect bind:value={type_of_event}>
                    <option value="company_events">Company events</option>
                    <option value="weddings">Weddings</option>
                    <option value="restaurants">Restaurants</option>
                    <option value="bars">Bars</option>
                    <option value="private_beaches">Private beaches</option>
                </MultiSelect>
            </div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="website">Website</label></div>
            <div class="basis-3/4"><input type="text" bind:value={website} /></div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="price">Price</label></div>
            <div class="basis-3/4"><input type="text" bind:value={price} /></div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="picture_url">Picture</label></div>
            <div class="basis-3/4"><input type="text" bind:value={picture_url} /></div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="video_url">Video</label></div>
            <div class="basis-3/4"><input type="text" bind:value={video_url} /></div>
        </div>
        <div class="lg:flex lg:flex-row">
            <div class="basis-1/4"><label for="short_description">Short description</label></div>
            <div class="basis-3/4"><input type="text" bind:value={short_description} /></div>
        </div>
    </div>
</form>
<button type="submit" on:click={sendData} on:click={submitted}>Send</button>