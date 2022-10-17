<script>
	// @ts-nocheck
	import { page } from '$app/stores';
	let id = $page.params.id;
	import FilmsStore from '../../stores/FilmsStore';

	let film;
	$FilmsStore.forEach((item) => {
		if (item.id === id) {
			film = item;
		}
	});
</script>

<svelte:head>
	<title>{film.title} - {film.release_date}</title>
</svelte:head>

<main>
	<figure
		style="background-image: url({film.movie_banner});"
		class="text-center bg-cover p bg-no-repeat bg-center"
	>
		<figure class="shadow p-8">
			<img class="w-80 m-auto p-4 pb-16" src={film.image} alt="{film.movie_title} poster" />
			<p class=" inline-block uppercase p-2 m-4 movie-title font-bold text-2xl tracking-wide">
				{film.title} ({film.release_date})
				<br />
				<span title={film.original_title_romanised}>{film.original_title}</span>
			</p>
			<br />
			<figcaption
				class="inline-block max-w-4xl p-2 m-4 movie-desc leading-8 font-bold text-lg tracking-wide"
			>
				{film.description}
				<br />
				{film.title} was produced by {film.producer} and directed by {film.director}. The movie has
				a running time of {film.running_time} minutes with a rating of {film.rt_score} on Rotten Tomatoes.
			</figcaption>
		</figure>
	</figure>
</main>

<style>
	main {
		color: #334137;
		font-family: 'Montserrat', sans-serif;
	}

	.movie-title {
		background-color: #c1d5b8;
	}

	.movie-desc {
		background-color: #c1d5b8;
	}

	.shadow {
		height: 100%;
		background-color: rgba(0, 0, 0, 0.4);
		width: 100%;
	}
</style>
