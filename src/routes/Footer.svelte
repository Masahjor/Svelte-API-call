<!-- ===== Script ===== -->
 <script lang="ts">

 </script>

<!-- ===== HTML ===== -->
  <footer>
    
    <figure>
        <!-- svelte-ignore a11y_img_redundant_alt -->
        <img src="AlexLogo.png" alt="logo photo" width="48" class="logo-pic">
    </figure>

  </footer>

<!-- ===== CSS ===== -->

<style>
    footer {
        background-color: navy;
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

</style>