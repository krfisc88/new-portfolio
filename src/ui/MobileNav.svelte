<script>
  import { slide } from "svelte/transition";
  import FaRegWindowClose from "svelte-icons/fa/FaRegWindowClose.svelte";
  import FaBars from "svelte-icons/fa/FaBars.svelte";
  export let brand = {};
  export let links = [];
  let hideNav = false;
  function toggleNav() {
    hideNav = !hideNav;
  }
</script>

{#if hideNav}
<div class="backdrop" on:click={toggleNav}/>
{/if}
<header class="nav-mobile">
  <div class="icon" on:click={toggleNav} >
    {#if !hideNav}
      <FaBars />
    {:else}
      <FaRegWindowClose />
    {/if}
  </div>
  {#if hideNav}
    <nav transition:slide>
      <div class="brand">
        <a href={brand.url} class="brand-link">
        {brand.title}
        </a>
      </div>
      <ul class="nav-list">
        {#each links as link}
          <li class="nav-item">
            <a class="nav-link" href="{link.url}">{link.title}</a>
          </li>
        {/each}
      </ul>
    </nav>
  {/if}
</header>

<style>
  .backdrop {
    height: 100vh;
    width: 100vw;
    position: absolute;
    background-color: rgba(0, 0, 0, 0.3);
    z-index: 10;
    overflow-y: hidden;
  }

  .nav-mobile {
    padding: 0.4em;
    background-color: #23001e;
    width: 100%;
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .icon {
    height: 2em;
    width: 2em;
    color: white;
    margin-left: auto;
  }

  .nav-mobile {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .brand {
    text-align: center;
    align-self: flex-end;
    color: white;
    font-size: 1.5em;
    margin-bottom: 0.5em;
    padding-bottom: 0.5em;
    border-bottom: 1px solid white;
  }

  .nav-list {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .nav-item {
    margin-bottom: 0.5em;
  }

  .nav-link {
    color: white;
    font-size: 1.5em;
  }
</style>