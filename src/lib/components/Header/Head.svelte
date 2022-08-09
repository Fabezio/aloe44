<script>
  import {page} from "$app/stores"
  import {currentPage} from "$lib/store"
  import {links} from "$lib/components/Header/links"

  const webSite = "aloe44"
  let title

  links.map(({url, text})=> {
    if (url == $currentPage) {
      console.log(text)
      return title = text
      
    }
  })
</script>

<svelte:head>
  <title>{webSite} | {title}</title>
</svelte:head>

<h1>{title}</h1>
