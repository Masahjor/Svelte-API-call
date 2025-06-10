<!-- ===== Script ===== -->
<script lang="ts">
    import '../app.css'
    import Header from './Header.svelte';
    import Main from './Main.svelte';
    import Footer from './Footer.svelte';

</script>


<!-- ===== HTML ===== -->
<main>

    <Header />
    <!-- this solution sucks ass, but it will have to do for now -->
    <div class="main-content">
    <Main />
    </div>
    <Footer />
        
</main>


<!-- ===== CSS ===== -->
 <style>

    :global(main) {
        height: auto;
    }

    :global(.main-content) {
        display: flex;
        justify-content: center;
        align-items: center;
        height: auto; /* Full viewport height */
    }

    :global(.grid-container) {
        display: grid;
        background: white;
        grid-template-columns: repeat(3, 1fr); /* Two columns */
        gap: 1rem; /* Adjust gap as needed */
        width: 1000px; /* Full width */
        height: 100%; /* Full height */
        padding-top: 15px;
    }

    :global(.grid-item) {
        background-color: lightgreen; /* Example background color */
        padding: 1rem;
        text-align: center;/* border: 1px solid green; */ /* Example border */
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        border-radius: 5px; /* Rounded corners */
        border-style: solid;

        & img {
            max-width: 100%;
            height: auto;
            display: block;
            margin: 0 auto;
    }

    :global(button) {
        background-color: green; /* GRØN */
        border: none;
        color: white;
        padding: 15px 32px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        border-radius: 5px;
        
        &:hover {
            background-color: yellow; /* JEG GRØNNER DEN */
            /* get pranked den er faktisk hul lol */
            color: black;
        }
    }
  }

      :global(h2) {
        font-size: 1.5rem;
        color: darkgreen;
        margin: 0.5rem 0;
    }

        :global(h3) {
        font-size: 1.3rem;
        color: white;
        background-color: darkgreen;
        padding: 3px 3px;
        border-radius: 5px;
        margin: 0.3rem 0;
    }

  :global(.item-invisible) {
    background-color: rgba(185, 230, 117, 0);
    color: rgba(185, 230, 117, 0);
    border: none;
    min-height: 120px;
  }
 </style>