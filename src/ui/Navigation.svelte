<script>
  import SideNav from "./SideNav.svelte";
  import MobileNav from "./MobileNav.svelte";
  export let links = [];
  export let brand = {};
  export let windowWidth = 0;
</script>

{#if windowWidth <= 640}
  <MobileNav {links} {brand}/>
{:else}
  <SideNav {links} {brand} />
{/if}

