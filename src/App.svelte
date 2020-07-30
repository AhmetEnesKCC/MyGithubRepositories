<script>
  import AppBar from "./components/AppBar.svelte";
  import Contents from "./components/Contents.svelte";

</script>

<style type="text/css">
:global(body) {
  margin: 0;
}
</style>

<svelte:head>
  <title>My Github Repos</title>
</svelte:head>

<AppBar />
<Contents/>

