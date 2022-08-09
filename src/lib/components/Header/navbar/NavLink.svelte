<script>
  import {page} from "$app/stores"
  // import {currentPage} from "$lib/store"
  export let navlink
  // import Nav from "$lib/components/Nav.svelte";
  // import Head from "$lib/components/Head.svelte";
  // console.log ("page", $page)
</script>

<div class="nav-item" class:active={$page.url.pathname == navlink.url}><a sveltekit:prefetch href={navlink.url} title={navlink.description} >{navlink.label}</a></div>

<style>
	.active a {
		color: black;
		text-shadow: 0 0px 5px lime;		
	}
</style>