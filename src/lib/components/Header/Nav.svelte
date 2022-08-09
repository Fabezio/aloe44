<script lang="ts">
	// import { page } from '$app/stores';
	import {links} from "./links"
	import Brand from "$lib/components/Header/navbar/Brand.svelte";
	import NavLink from "$lib/components/Header/navbar/NavLink.svelte";

</script>
<nav>
	<Brand />
	<!-- <div class="brand">
		<a href="/">
			<img src="img/logo_336_102124790.jpg" alt="Svelte">
			<span>Forme, bien-être et beauté</span>
		</a>
	</div> -->
	<div class="links">
		{#each links as navlink}
		<NavLink {navlink} />
		<!-- <div class="nav-item" class:active={$page.url.pathname === `/${url}`}><a sveltekit:prefetch href="/{url}" title={description} >{label}</a></div> -->
		{/each}
	</div>
</nav>

<style>
	nav {
		padding: 12px 8px;
		margin: 0 auto;
		display: grid;
		grid-gap: 1em;
		/* grid-template-columns: auto 1fr ;  */
		grid-template-areas: 
			"brand"
			"links";
		
		grid-template-rows: 2em, 2em;
		place-content: center center;
		place-items: center center;
		--background: rgba(255, 255, 255, 0.7);
	}


	.links {
		grid-area: links;
		display: flex;
		flex-direction: column;
		align-items: center;
		/* width: 100%; */
		justify-content: center;
		flex-wrap: wrap;
		flex: 0 0 auto;
	}
	
	@media screen and (min-width: 768px) {
		/* nav {
			grid-template-columns: auto 1fr 1fr;
		} */
	}
	/* @media screen and (min-width: 1024px) {
		nav {
			grid-template-columns: auto 1fr 1fr 1fr;
		}
	} */
	@media screen and (min-width: 1200px) {
		nav {
			grid-template-columns: auto 1fr ;
			grid-template-areas: "brand links";
			/* justify-content: start; */
		}
		.links {
			justify-self: end;
			/* display: flex; */
			flex-direction: row;
			justify-content: flex-end;
			flex: 1 0 100%;

		}
		/* .links */
	}


	</style>

