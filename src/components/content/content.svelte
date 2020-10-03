<script>
    import Social from '../social/social.svelte';
    import data from './content.data';

    const isLastInArray = (item, array) => array.lastIndexOf(item) === array.length - 1;
</script>

<style>
    h1 {
        margin-top: 0;
    }

    h1 span {
        font-size: 1.6rem;
        white-space: nowrap;
    }

    .container {
        width:100%;
        height: 100%;
        max-width: 20rem;
        max-height: 20rem;
        margin-left: 2rem;
    }

    @media (max-width: 767px) {
        h1 {
            font-size: 1.49rem;
            margin-top: 0;
        }

        h1 span {
            font-size: 1.3rem;
        }

		.container {
            width: unset;
            height: unset;
            margin-top: 2rem;
            margin-left: 0;
            padding-right: 2rem;
			padding-left: 2rem;
		}
	}
</style>

<div class={ 'container' }>
    <h1>
        { data.heading.title }
        <span>
            { data.heading.subtitle }
        </span>
    </h1>
    
    <p>{ data.description }</p>
    
    <p>
        { data.work.currentlyAt }
        <a 
            target={ '_blank' } 
            rel="noreferrer noopener"
            href={ data.work.jobs[0].href }>
            { data.work.jobs[0].title }.
        </a>
    </p>
    {#if data.work.jobs.length > 1} 
        <p>
            { data.work.previouslyAt }
            {#each data.work.jobs.slice(1) as job }
                <a 
                    target={ '_blank' } 
                    rel={ 'noreferrer noopener' }
                    href={ data.work.jobs[0].href }>
                    { data.work.jobs[0].title }{ isLastInArray(job, data.work.jobs) ? '.' : ', ' }
                    </a>
                
            {/each }
            
        </p>
    {/if}
    <Social />
</div>
