<script>
	// @ts-nocheck
	import FilmDetails from './FilmDetails.svelte';
	import FilmsStore from '../stores/FilmsStore';
</script>

<div class="container m-auto p-1 flex flex-wrap justify-center gap-8">
	{#each $FilmsStore as film}
		<FilmDetails {film} />
	{/each}
</div>
