<script>
  export let options
  export let value
  export let label
  export let name
</script>
  
<div class="inputfield">
  <label for={name}>{label}</label>
  <select id={name} bind:value={value}>
    <option value="">--choisissez--</option>
    {#each options as option}
    <option value={option.toLowerCase()}>{option}</option>
    {/each}
    
  </select>
</div>
