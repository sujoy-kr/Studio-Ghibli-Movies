<script>
	// @ts-nocheck
	export let film;
</script>

<a href="/{film.id}">
	<figure class="p-2 film-card rounded-lg w-60 text-center">
		<img class="w-full p-2 rounded-xl" src={film.image} alt="{film.title} poster" />
		<figcaption class="text-xs hover:text-white font-bold tracking-wide">
			{film.title}
		</figcaption>
	</figure>
</a>

<style>
	.film-card {
		background-color: #becfb6;
		transition: all 0.2s ease-in-out;
		color: #334137;
	}

	.film-card:hover {
		background-color: #768563;
		color: #ffffff;
	}
</style>
