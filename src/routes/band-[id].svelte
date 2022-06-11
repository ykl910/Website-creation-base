<script context='module'>
    import { auth, from, fromBucket } from '$lib/supabase';
    export async function load({params, fetch, session, stuff}) {
        try {
            console.log(params)
            let band_info = await from ('band').select().eq('id',params.id).single();
            console.log(params,band_info.data);
            return {props:band_info.data};
        } catch(error){
            return {error}
        }
    }
</script>

<script>
    export let type;
    export let name;
    export let email;
    export let type_of_event;
    export let short_description;
    export let mobile_number;
    export let number_of_members;
    export let website;
    let mainphoto = 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRnXx5dMcRzVvQPAvGw0ffq50Zp6HrPkA-gDw&usqp=CAU.png';
    let video = 'https://www.youtube.com/embed/CB3IvFjBKxs';
</script>

<div class="container mx-xl">

{#if name}

<div class="flex flex-row mb-12">
    <div class="basis-1/2">
        <div class="my-8">
            <p class="text-2xl font-bold">{name}</p>
            <p class="text-base">Genre: {type}</p>
        </div>
        <div class="my-8"> 
            <p class="text-base">{short_description}</p>   
        </div>
    </div>
    <div class="basis-1/2">
        <div class="mt-8">
            <img src = {mainphoto} class="w-full"  alt="band">
            <p class="text-sm">mayeb we can store image ULRs in the database so that each band detail page can show different images?</p>
        </div>
    </div>
</div>

<div class="mb-12">
    <div class="flex flex-row">
        <div class="basis-1/4 border-b py-8"><p class="text-base">Event</p></div>
        <div class="basis-3/4 border-b py-8"><p class="text-base">{type_of_event}</p></div>
    </div>
    <div class="flex flex-row">
        <div class="basis-1/4 border-b py-8"><p class="text-base">Contracts</p></div>
        <div class="basis-3/4 border-b py-8"><p class="text-base">1000€ add price in supabase</p></div>
    </div>
    <div class="flex flex-row">
        <div class="basis-1/4 border-b py-8"><p class="text-base">Member</p></div>
        <div class="basis-3/4 border-b py-8"><p class="text-base">{number_of_members}<br>member name here?</p></div>
    </div>
    {#if website}
    <div class="flex flex-row">
        <div class="basis-1/4 border-b py-8"><p class="text-base">Website</p></div>
        <div class="basis-3/4 border-b py-8"><p class="text-base">{website}</p></div>
    </div>
    {/if}
    <div class="flex flex-row">
        <div class="basis-1/4 border-b py-8"><p class="text-base">Contact</p></div>
        <div class="basis-3/4 border-b py-8"><p class="text-base">{email}<br>{mobile_number}</p></div>
    </div>
</div>

<p class="text-xl font-bold">Video</p>
<div class="my-8">
    <iframe width="560" height="315" src={video} 
            title="YouTube video player" frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
            allowfullscreen></iframe>
</div>

{:else}

<h1>This band is not available</h1>
{/if}

</div>