<!-- ===== SCRIPT ===== -->
<script lang="ts">
    let dogs: Array<{ url: string; id: string }> = [];

    const getDoggies = async () => {
        dogs = [];
        const res = await fetch('https://dog.ceo/api/breed/labrador/images/random/6');
        const dogJson = await res.json();
        console.log('Dog API response:', dogJson);
        dogs = dogJson.message.map((url: string, idx: number) => ({
            url,
            id: `dog-${idx + 1}`
        }));
    }
</script>

<!-- ===== HTML ===== -->
<div class="grid-container">
    <div class="grid-item" style="grid-column: span 3;">
        <h2>Dog API call</h2>
        <button on:click={getDoggies}>Get Doggies</button>
    </div>

    {#each dogs as dog}
        <div class="grid-item">
            <img src={dog.url} alt="dog" style="max-width:100%;max-height:100%;">
            <h2>{dog.id}</h2>
        </div>
    {/each}

<div class="grid-item item-invisible" style="grid-column: span 3;">
    <p>Secret text :)</p>
</div>

</div>


<!-- ===== End of code ===== -->