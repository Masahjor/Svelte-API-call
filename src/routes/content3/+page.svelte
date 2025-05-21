<!-- Script -->
<script lang="ts">

    import Header from '../Header.svelte';
    import Main from './Main.svelte';
    import Footer from '../Footer.svelte';
    let { children } = $props();
</script>

<!-- HTML -->
<main>
    <Header />
    <div class="main-content">
    <Main />
    </div>
    <Footer />
</main>


<!-- CSS -->
<style>
    
</style>


<!-- End of code snippet -->