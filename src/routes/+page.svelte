<script>
  import PageConnect from "$lib/components/MainPage/PageConnect.svelte";
  import PageHero from "$lib/components/MainPage/PageHero.svelte";
  import PopUp from "../lib/components/PopUp.svelte";
</script>

<svelte:head>
  <title>Pro - Stud | Upload Projects</title>
  <meta name="description" content="Students upload Projects & Get Hire" />
  <meta name="keywords" content="Students, Projects, Hire, Upload, Pro-Stud" />
  <meta
    name="og:image"
    content="https://cdn-icons-png.flaticon.com/512/1091/1091885.png"
  />
</svelte:head>
<main>
  <PageHero />
  <PageConnect />
  <PopUp />
</main>

<!-- <style lang="postcss"> -->
<!-- </style> -->
