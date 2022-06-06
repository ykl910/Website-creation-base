<script context='module'>
    import { auth, from, fromBucket } from '$lib/supabase';
    export async function load({params, fetch, session, stuff}) {
        try {
            console.log(params)
            let band_info = await from ('band').select().eq('name',params.name).single();
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
</script>

{#if name}
    
<h1>This is {name} band, please contact them on {email}</h1>

{:else}

<h1>This band is not available</h1>
{/if}
