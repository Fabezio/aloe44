<script>
  import {createEventDispatcher} from 'svelte'
  const dispatch = createEventDispatcher()
  export let submit = false
  export let reset = false
</script>

{#if submit}
<button class="bg-blue" type="submit" >
  <slot />
  </button>
{:else if reset}
<button class="bg-gold" type="reset" >
  <slot />
  </button>
{:else}
<button on:click={()=>dispatch('click')}  >
  <slot />
  </button>
{/if}


<style>
  button {
    border: 1px solid #ccc;
    width: 100%;
    border-radius: 7px;
    padding: 16px 10px;
    margin: 10px 1px;
    /* background-color: #fff; */
    /* color: #333; */
    font-size: 15px;
    /* font-weight: */
    font-weight: 400;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }
</style>