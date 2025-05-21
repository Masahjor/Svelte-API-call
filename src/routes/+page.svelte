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
        height: 1000px; /* Full viewport height */
    }

    :global(.grid-container) {
        display: grid;
        background: lightgreen;
        grid-template-columns: repeat(3, 1fr); /* Two columns */
        gap: 1rem; /* Adjust gap as needed */
        width: 1000px; /* Full width */
        height: 100%; /* Full height */
    }

    :global(.grid-item) {
        background-color: #f0f0f0; /* Example background color */
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

  }
 </style>