<script>
	import Photo from './components/photo/photo.svelte';
	import Content from './components/content/content.svelte';
	import SEO from './components/seo/seo.svelte';
</script>

<main>
		<!-- <SEO /> -->
		<Photo />
		<Content />	
</main>

<style>
	main {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: row;
	}

	@media (max-width: 767px) {
		main {
			flex-direction: column;
		}
	}
</style>