<script lang="ts">
	import { page } from '$app/state';

	const onDesignFive = $derived(page.url.pathname === '/5');
</script>

<a
	class="design-toggle"
	href={onDesignFive ? '/3' : '/5'}
	aria-label={onDesignFive ? 'Switch to design 3' : 'Switch to design 5'}
>
	Design {onDesignFive ? '3' : '5'} <span aria-hidden="true">↗</span>
</a>

<style>
	.design-toggle {
		position: fixed;
		right: 16px;
		bottom: 16px;
		z-index: 100;
		display: inline-flex;
		align-items: center;
		gap: 8px;
		padding: 9px 12px;
		border: 1px solid #d1d1d1;
		border-radius: 4px;
		background: #fff;
		color: #222;
		box-shadow: 0 2px 10px #0002;
		font: 600 12px/1 Arial, sans-serif;
		text-decoration: none;
	}

	.design-toggle:hover,
	.design-toggle:focus-visible {
		background: #222;
		color: #fff;
	}
</style>
