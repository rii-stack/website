<script lang="ts">
	import { invalidateAll } from '$app/navigation';
	import { page } from '$app/stores';

	import Button from '$lib/components/Button.svelte';

	import { errorContent } from '$lib/constants';
</script>

<section class="wrapper">
	<div class="container">
		<h1 class="title">{errorContent.title}</h1>

		<div class="info">
			<p class="message">{$page.error?.message}</p>
			<Button type="button" variant="primary" on:click={invalidateAll}
				>{errorContent.buttonText}</Button
			>
		</div>
	</div>
</section>

<style lang="scss">
	@use '$styles/mixins' as *;

	.wrapper {
		padding: var(--space-6) 0;
		min-height: 100vh;
		position: relative;
		display: flex;
		justify-content: center;
		align-items: center;
		overflow: hidden;

		@include respond-to('lg') {
			padding: var(--space-8) 0;
		}
	}

	.container {
		@include container(64rem);
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		gap: var(--space-2) 0;

		@include respond-to('lg') {
			gap: var(--space-4) 0;
		}
	}

	.info {
		display: flex;
		flex-direction: column;
		gap: var(--space-2);
	}

	.title {
		font-size: var(--fs-xxl);
		font-weight: var(--fw-black);
		line-height: var(--lh-tight);
		color: var(--clr-white);
		text-align: center;
		cursor: pointer;

		@include respond-to('lg') {
			font-size: var(--fs-xxxl);
		}
	}

	.message {
		font-size: var(--fs-base);
		font-weight: var(--fw-normal);
		line-height: var(--lh-tight);
		color: var(--clr-grey);
		text-align: center;
	}
</style>
