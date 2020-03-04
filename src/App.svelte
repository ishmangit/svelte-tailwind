<script>
  import router from 'page';
  import Home from './routes/Home.svelte';
  import About from './routes/About.svelte';
  export let name;
  let page;
  let params;
  router('/home', () => page = Home);
  router('/about', () => page = About);
  router.start();
</script>

<style lang="postcss">
  .green-color {
    @apply bg-green-700;
  }
</style>

<div class="green-color">
  <h1>Hello {name}!</h1>
</div>
<a href="/home">Home</a>
<a href="/about">About</a>
<svelte:component this={page} params={params} />
