<script lang="ts">
  import Nav from '../components/core/Nav.svelte';
</script>

  <Nav/>
  <slot /> 

<style>
  /* :global(body) {
    background-color: #15251fe4;
    overflow: hidden;
  } */

  #layout {
    /* position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden; */
  }
</style>
