<script>
  export let value = ""
  export let name = ""
  export let label = ""
</script>
  
<div class="textareafield">
  <label for={name}>{label} <sup>*</sup></label>
  <textarea id={name} type="text" bind:value={value} rows=3 />
</div>

<style>
  
</style>