<script>
  export let type = "submit";
</script>

<button {type} class={type} >
  <slot/>
</button>

<style>
  button {
    padding: 0.3em 1em;
  }
  .submit {
  }
</style>