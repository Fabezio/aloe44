<script lang="ts">
	import { page } from '$app/stores';
	import {links} from "./links"

</script>
<nav>
	<div class="brand">
		<a href="/">
			<img src="img/logo_336_102124790.jpg" alt="Svelte">
			<span>Forme, bien-être et beauté</span>
		</a>
	</div>
	<div class="links">
		{#each links as {url, text}}
		<div class="nav-item" class:active={$page.url.pathname === `/${url}`}><a sveltekit:prefetch href="/{url}">{text}</a></div>
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
	nav a {
		height: 100%;
		align-items: center;
		padding: 2px 1em;
		color: var(--heading-color);
		font-size: 0.9rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}
	.brand {
		grid-area: brand;
	}
	
	
	.brand a {
		display: flex;
		font-weight: 600;
		text-transform: uppercase;
		
	}
	
	.brand img {
		height: 56px;
		margin-right: 8px;
	}
	
	.brand span {
		vertical-align: middle;
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
	.links a {
		font-weight: 500;
		color: gray;
	}
	
	
	.active a {
		color: black;
		text-shadow: 0 0px 5px lime;		
	}
	
	a:hover {
		color: var(--accent-color);
	}
	
	@media screen and (min-width: 768px) {
		nav {
			/* grid-template-columns: auto 1fr 1fr; */
		}
	}
	@media screen and (min-width: 1024px) {
		nav {
			/* grid-template-columns: auto 1fr 1fr 1fr; */
		}
	}
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

