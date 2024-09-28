<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	export let variant: 'primary' | 'secondary' = 'primary';

	const dispatch = createEventDispatcher();
</script>

<button
	class="wrapper"
	class:primary={variant === 'primary'}
	class:secondary={variant === 'secondary'}
	on:click={() => dispatch('click')}
	{...$$props}
>
	<slot />
</button>

<style lang="scss">
	@use '$styles/mixins' as *;

	.wrapper {
		position: relative;
		display: inline-block;
		font-size: var(--fs-base);
		font-weight: var(--fw-bold);
		line-height: var(--lh-tight);
		text-transform: uppercase;
		text-align: center;

		&:disabled {
			opacity: 0.5;
			pointer-events: none;
		}
	}

	.primary {
		padding: var(--space-2) var(--space-4);
		background-color: var(--clr-white);
		border-radius: var(--br-lg);
		color: var(--clr-black);
	}

	.secondary {
		padding: var(--space-2) var(--space-4);
		background-color: transparent;
		border: 2px solid var(--clr-white);
		border-radius: var(--br-lg);
		color: var(--clr-white);
	}
</style>
