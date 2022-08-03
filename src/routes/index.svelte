<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="ts">
	import Counter from '$lib/Counter.svelte';
	import Head from "$lib/components/Head.svelte";
	const images = [
		[
			{img: '47867005', url: "http://indd.adobe.com/view/4101c945-e727-40d5-b0c8-8bde9cab4dc5", text: ""},
			{img: "47867035", url: "http://indd.adobe.com/view/ad1f9502-dbee-4495-afd8-094baf68a415", text: ""},
		],
		[
			{img: 'big_47867690_0_800-274', text: "pour le cosmétique", url: "https://info.fredericm.com/cosmetiques?ref=vhj6kambk2qrbvgdnx3q8v5ub8"},
			{img: "big_47867710_0_350-307", text: "pour le bien-être", url: "https://info.fredericm.com/feelgood?ref=vhj6kambk2qrbvgdnx3q8v5ub8"},
			{img: "47867765", text: "pour les bijoux", url: "https://info.fredericm.com/silver?ref=vhj6kambk2qrbvgdnx3q8v5ub8"},
		],
	]

</script>
<Head title="Forme, bien-être et beauté" />
<section>
	<figure>
		<img src="img/home/big_47867890_0_600-114.JPG" alt="">
		<figcaption>
			<a href="mailto:contact@aloe44.com" >contact@aloe44.com</a> ou  06 82 21 91 24 ou 06 82 21 91 24
	
		</figcaption>
	</figure>
</section>
	
<section>
	<div class="grid">
		{#each images[0] as {img, url}}
		<div class="thumbnail">
		<a href={url} target="_blank">
				<img src="img/home/{img}.JPG" width="300" alt="image" >
			</a>
		</div>
		{/each}
	</div>
</section>

<section>
	<p class="green center">
		Pour plus de détail, consultez les pages suivantes :

	</p>
	<div class="rows">
		{#each images[1] as {text, img, url}}
		<div class="">
			<p class="green">{text}</p>
		<a href={url} target="_blank">
				<img src="img/home/{img}.JPG"  alt="image" >
			</a>
		</div>
		{/each}
	</div>
</section>
<section>
	<p class="green center">
		Avertissement : Nos produits ne peuvent en aucun cas remplacer un traitement médical.
		<br>
		Conformément à la loi, en tant que VDI, les tarifs sont absents du site afin de préserver les droits du consommateur. Pour toute commande, merci de nous contacter.
		<br>
		Satisfait ou remboursé sous 30 jours.
	</p>

</section>
<section>
<p>
	Chrystelle LOSTANLEN<br>	
	31 rue du Marquis de Dion<br>
	44470 Carquefou<br>
	<!-- 06 82 21 91 24 ou 06 82 21 91 24<br>
	02 40 49 69 33 ou 02 40 49 69 33<br> -->
	</p>
	<p>
	Distributeur indépendant Frédéric M
</p>
</section>

<section  class="mx-center" >
<p>
Maquillage, parfums, cosmétique, bio, france, bien être...<br>
Déplacement à domicile sur Nantes et sa région (Pays de la Loire, Loire Atlantique, Vendée, Maine et Loire, Sarthe, Mayenne, Vertou, Saint Sébastien, La chapelle sur Erdre, Sucé sur Erdre, Orvault, Saint Herblain, Rezé...)
	</p>
</section>





<style>
	section {
		margin: 3em 0;
	}
	figure, .thumbnail {
		margin: auto 1em;
		width: auto;
		text-align: center;
	}
	.thumbnail {
		width: 300px;
	}
	
	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		grid-gap: 1em;
	}
	.rows {
		justify-items: center;
		display: grid;
		grid-template-rows: repeat(auto-fit, minmax(300px, 1fr));
		/* grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); */
		grid-gap: 1em;
	}
	.rows p {
		text-align: center;
	}
	.center
	{ text-align: center;	}
</style>