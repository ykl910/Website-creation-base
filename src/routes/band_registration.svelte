


<script>
    import  supabaseClient  from '../../src/lib/supabase';

    let name, type, mobile;
    const sendData = async () => {
        const { data, error } = await supabaseClient
            .from('band')
            .insert({ name, type, mobile })

        return { data, error };
    };
</script>

<form action="" on:submit|preventDefault={sendData}>
    <div class="container">
        <label for="name">Name</label>
        <input type="text" bind:value={name} />
    </div>
    <div class="container">
        <label for="type">type</label>
        <input type="text" bind:value={type} />
    </div>
    <div class="container">
        <label for="mobile">mobile</label>
        <input type="text" bind:value={mobile} />
    </div>

    <button type="submit">Send</button>
</form>