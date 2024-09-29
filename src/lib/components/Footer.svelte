<script lang="ts">
	import { footerContent } from '$lib/constants';
</script>

<footer class="wrapper">
	<a class="link" href={`mailto:${footerContent.linkText}`}>{footerContent.linkText}</a>
</footer>

<style lang="scss">
	@use '$styles/mixins' as *;

	.wrapper {
		position: fixed;
		bottom: var(--space-6);
		left: 50%;
		transform: translateX(-50%);
		display: flex;
		justify-content: center;

		@include respond-to('lg') {
			bottom: var(--space-8);
		}
	}

	.link {
		font-size: var(--fs-base);
		font-weight: var(--fw-normal);
		line-height: var(--lh-tight);
		color: var(--clr-grey);
		text-align: center;
		opacity: 0.7;
	}
</style>
