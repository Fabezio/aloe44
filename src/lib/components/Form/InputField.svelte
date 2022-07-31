<script>
  export let value = ""
  export let name = ""
  export let label = ""
  
  
  // export let placeholder = ""
  export let entryType = "text"
  export let multiple = false
const  types = [
  "number",
  "tel",
  "email",
  // "text",
  "password",
  "date",
  "datetime-local",
  "month",
  "time",
  "week",
  "url",
  "search",
  "color",
  "file",
  "range",
  // "checkbox",
  // "radio",
  // "submit",

]
</script>

<div class="inputfield">
  <label for={name}>{label}</label>
  {#if entryType=="" || entryType=="text"}
  <input id={name} name={name} bind:value={value} placeholder={label} type="text">
  {:else if entryType=="number"}
  <input id={name} type="number" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="tel"}
  <input id={name} type="tel" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="email"}
  <input id={name} type="email" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="password"}
  <input id={name} type="password" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="date"}
  <input id={name} type="date" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="datetime-local"}
  <input id={name} type="datetime-local" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="time"}
  <input id={name} type="time" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="week"}
  <input id={name} type="week" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="url"}
  <input id={name} type="url" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="search"}
  <input id={name} type="search" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="color"}
  <input id={name} type="color" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="range"}
  <input id={name} type="range" name={name} bind:value={value} placeholder={label} >
  {:else if entryType=="file"}
  <input id={name} type="file" {multiple} name={name} bind:value={value} placeholder={label} >
  {/if}
</div>

<style>
  
</style>