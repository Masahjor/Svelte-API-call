<!-- ===== Script ===== -->
<script lang="ts">
    let kittens: Array<{ url: string; id: string }> = [];

    const getKittens = async () => {
        kittens = [];
        const res = await fetch('https://api.thecatapi.com/v1/images/search?limit=3');
        const kittenJson = await res.json();
        console.log('Kittens API response:', kittenJson);
        kittens = kittenJson.slice(0, 3);
    }
</script>

<!-- ===== HTML ===== -->
<div class="grid-container">
    <div class="grid-item" style="grid-column: span 3;">
        <h2>Welcome to SvelteKit, visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</h2>
        <h1>API get missekat</h1>
        <button on:click={getKittens}>Get missekat</button>
    </div>

    <div class="grid-item" style="grid-column: span 3;">
        <img src="AlexLogo.png" alt="img">
    </div>

    <!-- Show kittens here -->
    {#each kittens as kitten}
        <div class="grid-item">
            <img src={kitten.url} alt="kitten" style="max-width:100%;max-height:100%;">
            <h2>{kitten.id}</h2>
        </div>
    {/each}

</div>

<!-- ===== End of code ===== -->