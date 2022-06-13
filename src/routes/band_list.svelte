<h1>This page displays all the bands in form of blocks</h1>

<script context='module'>
    import  supabaseClient  from '../../src/lib/supabase';
    let name, type_of_music, mobile_number, email, number_of_members, website, short_description, type_of_event;
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
</script>

    
<h1>This is {name} band, please contact them on {email}</h1>
<p>{bands.length}</p>
{#each bands as band}
    <p>{band.name}</p>
{/each}
