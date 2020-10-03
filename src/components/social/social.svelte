<script>
    import data from './social.data.js';
</script>

<style>
    .social {
        margin-top: 8.5rem;
        display: flex;
    }

    .icon {
        max-width: 2rem;
        margin: 0 1.5rem 0 0;
    }

    @media (max-width: 767px) {
        .social {
            margin-top: 2rem;
        }
	}
</style>

<div class={ 'social' }>
    { #each data.links as link }
        <a
            target={ '_blank' }
            rel={ 'noreferrer noopener' }
            href={ link.href }>
            <img 
                class={ 'icon' } 
                alt={ link.alt }
                src={ link.src } />
        </a>
        {/each}
</div>