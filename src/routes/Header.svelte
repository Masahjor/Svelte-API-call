<!-- ===== Script ===== -->
 <script lang="ts">
    let sections = [
        { name: "Section 1", path: "/" },
        { name: "Section 2", path: "/content2" },
        { name: "Section 3", path: "/content3" }
    ];
 </script>

<!-- ===== HTML ===== -->
  <header>
    
    <figure>
        <!-- svelte-ignore a11y_img_redundant_alt -->
        <img src="AlexLogo.png" alt="logo photo" width="48" class="logo-pic">
    </figure>

    <!-- to do: get the navigation bar to actually function. I am about to shit my pants. -->
    <nav>
        <ul>
            {#each sections as section}
            <li>
                <a href={section.path}>{section.name}</a>
            </li>
            {/each}
        </ul>
    </nav>

  </header>

<!-- ===== CSS ===== -->

<style>
    header {
        background-color: limegreen;
        color: black;
        padding: 1em;
        display: flex;
        align-items: center;
        justify-content: space-between;
    
        & figure {
            display: inline-block; /* Ensure it doesn't stretch */
        }
    
    }

    .logo-pic {
        max-width: 100%; /* Ensure responsiveness */
        height: auto;
    }

    nav ul {
        list-style-type: none;
        margin: 0;
        padding: 0;
    }

    nav ul li {
        display: inline;
        margin-right: 1rem;
    }

    nav ul li a {
        color: black;
        text-decoration: none;
    }

    nav ul li a:hover {
        text-decoration: underline;
        color: yellow;
    }
</style>