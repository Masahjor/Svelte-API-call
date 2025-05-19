<!-- ===== Script ===== -->
 <script lang="ts">
    let sections = [
        { title: "Section 1", content: "/" },
        { title: "Section 2", content: "/content2" },
        { title: "Section 3", content: "/content3" }
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
        background-color: lime;
        color: white;
        padding: 1em;
        display: flex;
        align-items: center;
        justify-content: space-between;
        /* height: auto;
        margin: auto;
        text-align: center; */
    
        & figure {
            margin: 0 auto; /* Center the figure element */
            display: inline-block; /* Ensure it doesn't stretch */
        }
    
    }

    .logo-pic {
        max-width: 100%; /* Ensure responsiveness */
        height: auto;
        padding-bottom: 15px;
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
        color: white;
        text-decoration: none;
    }

    nav ul li a:hover {
        text-decoration: underline;
    }
</style>