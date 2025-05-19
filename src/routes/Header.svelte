<!-- ===== Script ===== -->
 <script lang="ts">
    let sections = [
        { title: "Section 1", content: "Content for section 1" },
        { title: "Section 2", content: "Content for section 2" },
        { title: "Section 3", content: "Content for section 3" }
    ];
 </script>

<!-- ===== HTML ===== -->
  <header>
    
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
        /* height: auto;
        margin: auto;
        text-align: center; */
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