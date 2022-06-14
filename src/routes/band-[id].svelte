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
    export let name;
    export let email;
    export let type_of_music;
    export let type_of_event;
    export let short_description;
    export let mobile_number;
    export let website;
    export let price;
    export let picture_url;
    export let video_url;
</script>

{#if name}

<div class="md:flex md:flex-row mb-12">
    <div class="basis-1/2">
        <div class="my-8">
            <h1>{name}</h1>
            <p>{#if type_of_music}Genre: {type_of_music}{:else}No specific genre{/if}</p>
        </div>
        <div class="my-8"> 
            <p>{short_description}</p>   
        </div>
    </div>
    <div class="basis-1/2">
        <div class="mt-8">
            <img src = {picture_url} class="w-full"  alt="band">
        </div>
    </div>
</div>

<div class="mb-12">
    <div class="md:flex md:flex-row">
        <div class="basis-1/4 md:border-b py-8"><p>Event</p></div>
        <div class="basis-3/4 border-b py-8"><p>{type_of_event}</p></div>
    </div>
    <div class="md:flex md:flex-row">
        <div class="basis-1/4 md:border-b py-8"><p>Contracts</p></div>
        <div class="basis-3/4 border-b py-8"><p>{price}€</p></div>
    </div>
    {#if website}
    <div class="md:flex md:flex-row">
        <div class="basis-1/4 md:border-b py-8"><p>Website</p></div>
        <div class="basis-3/4 border-b py-8"><p>{website}</p></div>
    </div>
    {/if}
    <div class="md:flex md:flex-row">
        <div class="basis-1/4 md:border-b py-8"><p>Contact</p></div>
        <div class="basis-3/4 border-b py-8"><p>{email}<br>{mobile_number}</p></div>
    </div>
    {#if video_url}
    <div class="md:flex md:flex-row">
        <div class="basis-1/4 py-8"><p>Video</p></div>
        <div class="basis-3/4 py-8 responsive-youtube"><iframe height=100% src = {video_url}
            title="YouTube video player" frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
            allowfullscreen></iframe></div>
    </div>
    {/if}
</div>
{:else}

<h1>This band is not available</h1>
{/if}