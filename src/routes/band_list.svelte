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
    export let name;
    export let bands;
    export let type_of_music;
    export let mobile_number;
    export let email;
    export let number_of_members;
    export let website;
    export let type_of_event;
    export let short_description;
    export let video_url;
</script>

    
<p>{bands.length}</p>
{#each bands as band}
    <p>{band.name}</p>
    <p>{band.bands}</p>
    <p>{band.type_of_music}</p>
    <p>{band.video_url}</p>
{/each}