<script>
	import FilmList from '$lib/FilmList.svelte';
	import Footer from '$lib/Footer.svelte';
	import Header from '$lib/Header.svelte';
	import LoadingText from '$lib/LoadingText.svelte';
	import FilmsStore from '../stores/FilmsStore';

	(async () => {
		const response = await fetch('https://ghibliapi.herokuapp.com/films');
		const data = await response.json();
		$FilmsStore = data;
	})();
</script>

<svelte:head>
	<title>Studio Ghibli</title>
</svelte:head>

<Header />

{#if $FilmsStore}
	<FilmList />
{:else}
	<LoadingText />
{/if}

<Footer />
