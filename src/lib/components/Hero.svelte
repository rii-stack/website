<script lang="ts">
	import { heroContent } from '$lib/constants';
</script>

<section class="wrapper">
	<div class="container">
		<h1 class="title rainbow-text">{heroContent.title}</h1>
		<p class="description">{heroContent.description}</p>
	</div>
</section>

<style lang="scss">
	@use '$styles/mixins' as *;

	.wrapper {
		padding: var(--space-6) 0;
		min-height: 100vh;
		position: relative;
		display: flex;
		flex-direction: column;
		justify-content: center;
		overflow: hidden;

		@include respond-to('lg') {
			padding: var(--space-8) 0;
		}
	}

	.container {
		@include container(64rem);
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: var(--space-2) 0;

		@include respond-to('lg') {
			gap: var(--space-4) 0;
		}
	}

	.title {
		font-size: var(--fs-xxl);
		font-weight: var(--fw-black);
		line-height: var(--lh-tight);
		text-align: center;
		cursor: pointer;

		@include respond-to('lg') {
			font-size: var(--fs-xxxl);
		}
	}

	.description {
		max-width: calc(64rem / 2);
		width: 100%;
		font-size: var(--fs-base);
		font-weight: var(--fw-normal);
		line-height: var(--lh-normal);
		color: var(--clr-grey);
		text-align: center;
	}

	.rainbow-text {
		background-color: var(--clr-blue);
		background-image: linear-gradient(
			45deg,
			#4a90e2 16.666%,
			#50b3e6 16.666%,
			#50b3e6 33.333%,
			#74c7e6 33.333%,
			#74c7e6 50%,
			#67b3a3 50%,
			#67b3a3 66.666%,
			#5a6f9e 66.666%,
			#5a6f9e 83.333%,
			#7b5ea4 83.333%
		);

		background-size: 100%;
		background-repeat: repeat;

		/* Use the text as a mask for the background. */
		/* This will show the gradient as a text color rather than element bg. */
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;

		animation: static-rainbow-text var(--transition-700) ease forwards;

		&:hover {
			animation: dynamic-rainbow-text var(--transition-500) ease-in forwards;
		}
	}

	/* Move the background and make it smaller. */
	@keyframes static-rainbow-text {
		0% {
			background-size: 650%;
		}
		40% {
			background-size: 650%;
		}
		100% {
			background-size: 100%;
		}
	}

	/* Move the background and make it larger. */
	@keyframes dynamic-rainbow-text {
		0% {
			background-size: 100%;
		}
		80% {
			background-size: 650%;
		}
		100% {
			background-size: 650%;
		}
	}
</style>
