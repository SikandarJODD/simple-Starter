<script>
  import "../app.css";
  import Navbar from "$lib/components/Navbar.svelte";
</script>

<Navbar />
<slot />

<style>
  /* :global(main) {
    padding: 0px 10%;
  } */
</style>
