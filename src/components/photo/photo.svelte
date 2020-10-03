<script>
    import data from './photo.data.js';
</script>

<style>
    .image {
        max-width: 20rem;
        max-height: 20rem;
    }

    @media (max-width: 767px) {
		.image {
            width: 18rem;
            height: 18rem;
        }
	}
</style>

<img  class={ 'image' } src={ data.image.src } alt={ data.image.alt } />