<script lang="ts">
	import Title from '$lib/components/Title.svelte';

	import { heroContent } from '$lib/constants';
</script>

<section class="wrapper">
	<div class="container">
		<Title titleText={heroContent.title} />
		<div class="info">
			<p class="description">{heroContent.description}</p>
			<a class="link" href={`mailto:${heroContent.linkText}`}>{heroContent.linkText}</a>
		</div>
	</div>
</section>

<style lang="scss">
	@use '$styles/mixins' as *;

	.wrapper {
		padding: var(--space-8) 0;
		min-height: 100vh;
		position: relative;
		display: flex;
		justify-content: center;
		align-items: center;
		overflow: hidden;

		@include respond-to('lg') {
			padding: var(--space-12) 0;
		}
	}

	.container {
		@include container(64rem);
		display: flex;
		flex-direction: column;
		gap: var(--space-4) 0;

		@include respond-to('lg') {
			gap: var(--space-6) 0;
		}
	}

	.info {
		display: flex;
		flex-direction: column;
		justify-content: center;
		gap: var(--space-4) 0;
	}

	.description {
		font-size: var(--fs-base);
		font-weight: var(--fw-regular);
		line-height: var(--lh-condensed);
		color: var(--clr-grey);
		text-align: center;
	}

	.link {
		font-size: var(--fs-base);
		font-weight: var(--fw-bold);
		line-height: var(--lh-tight);
		color: var(--clr-grey);
		text-align: center;
	}
</style>
