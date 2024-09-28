<script lang="ts">
	export let titleText: string = '';
</script>

<h1 class="title rainbow-title">{titleText}</h1>

<style lang="scss">
	@use '$styles/mixins' as *;

	.title {
		display: block;
		font-size: var(--fs-xxl);
		font-weight: var(--fw-black);
		line-height: var(--lh-tight);
		text-align: center;
		cursor: pointer;

		@include respond-to('lg') {
			font-size: var(--fs-xxxl);
		}
	}

	.rainbow-title {
		background-color: var(--clr-red);
		background-image: linear-gradient(
			45deg,
			#ca4246 16.666%,
			#e16541 16.666%,
			#e16541 33.333%,
			#f18f43 33.333%,
			#f18f43 50%,
			#8b9862 50%,
			#8b9862 66.666%,
			#476098 66.666%,
			#476098 83.333%,
			#a7489b 83.333%
		);

		background-size: 100%;
		background-repeat: repeat;

		/* Use the text as a mask for the background. */
		/* This will show the gradient as a text color rather than element bg. */
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;

		animation: static-rainbow-title var(--transition-700) ease forwards;

		&:hover {
			animation: moving-rainbow-title var(--transition-500) ease-in forwards;
		}
	}

	/* Move the background and make it smaller. */
	@keyframes static-rainbow-title {
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
	@keyframes moving-rainbow-title {
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
