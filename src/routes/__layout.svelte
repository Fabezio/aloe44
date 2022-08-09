<script lang="ts">
	import Header from '$lib/components/Header/index.svelte';
	import {page} from '$app/stores';
	import {currentPage} from "$lib/store"
	$currentPage = $page.url.pathname
	// import Nav from '$lib/components/Nav.svelte';
	import '../app.css';
	$: innerWidth = 0
	$: innerHeight = 0
	$: outerWidth = 0
	$: outerHeight = 0
	
	// $: if (innerHeight > 0) console.log("Dimensions internes:",innerWidth, innerHeight)
	// $: if (outerHeight > 0) console.log("Dimensions externes:",outerWidth, outerHeight)
</script>
<svelte:window 
	bind:innerHeight 
	bind:innerWidth
	bind:outerHeight 
	bind:outerWidth
 />

<Header />
<div id="top"></div>
<div class="container">

	<main>
		<slot />
	</main>
	
	<footer>
		<p><a href="#top" >Top</a>
			<br>
	
	Vendeur Distributeur Indépendant
	<br>
	contact@aloe44.com</p>
		<!-- <p>visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to learn SvelteKit</p> -->
	</footer>
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>
