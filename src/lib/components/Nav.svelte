<script lang="ts">
	import { page } from '$app/stores';
	import {links} from "./links"

</script>
<nav>
	<div class="brand">
		<a href="/">
			<img src="img/_common/logo_336_102124790.jpg" alt="Svelte">
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
		display: grid;
		grid-template-columns: auto 1fr ; 
		place-content: center stretch;
		--background: rgba(255, 255, 255, 0.7);
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
		display: flex;
		align-items: center;
		width: 100%;
		justify-content: flex-end;
		flex: 0 0 auto;
	}
	.links a {
		font-weight: 500;
		color: gray;
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
	.active a {
		color: black;
		text-shadow: 0 0px 5px lime;		
	}
	
	a:hover {
		color: var(--accent-color);
	}
</style>

