<script>
  import {createEventDispatcher} from "svelte"
  import Button from "$lib/components/Button.svelte";
  const dispatch = createEventDispatcher()
</script>

<form on:submit|preventDefault={()=> dispatch("submit")}>
  <slot/>
  
    <div class="flex">
      <Button submit >valider</Button>
      <Button reset >vider</Button>
      
    </div>
</form>

<style>
  form {
    margin: 0 auto;
  }
  @media (min-width: 768px) {
    form {
      width: 768px;
    }
  }
</style>