<!-- ===== Script ===== -->
<script lang="ts">
    const getKittens = async()=> {
        const res = await fetch('https://api.thecatapi.com/v1/images/search?limit=10');
        const kittenJson = await res.json();
        console.log(kittenJson);
    }
</script>

<!-- ===== HTML ===== -->
    <div class="grid-container">
        <div class="grid-item" style="grid-column: span 3;">
            <p>Welcome to SvelteKit, visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>
            <h1>API get missekat</h1>
            <button on:click={getKittens}>Get missekat</button>
        </div>
        <div class="grid-item" style="grid-column: span 3;">
            <img src="AlexLogo.png" alt="img">
        </div>

        <div class="grid-item">
            <h2>Item 1</h2>
            <p>Content for item 1</p>
        </div>

        <div class="grid-item">
            <h2>Item 2</h2>
            <p>Content for item 2</p>
        </div>

        <div class="grid-item">
            <h2>Item 3</h2>
            <p>Content for item 3</p>
        </div>
    </div>

<!-- ===== End of code ===== -->