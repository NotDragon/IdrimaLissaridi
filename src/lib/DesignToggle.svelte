<script lang="ts">
	import { page } from '$app/state';

	const designs = ['1', '3', '5'];
	const current = $derived(page.url.pathname.split('/')[1] || '1');
	const next = $derived(designs[(designs.indexOf(current) + 1) % designs.length]);
</script>

<a class="design-toggle" href="/{next}" aria-label="Switch to design {next}">
	<span class="label">DESIGN {current}</span>
	<span class="separator" aria-hidden="true"></span>
	<span>VIEW {next} <span aria-hidden="true">↗</span></span>
</a>

<style>
	.design-toggle{position:fixed;left:18px;bottom:18px;z-index:100;display:inline-flex;align-items:center;gap:10px;padding:11px 13px;border:1px solid #d6d1c6;border-radius:3px;background:#fff;color:#183d2d;box-shadow:0 3px 16px #0002;font:700 11px/1.1 Arial,sans-serif;letter-spacing:.08em;text-decoration:none}
	.separator{width:1px;height:14px;background:#c7c8bc}
	.label{color:#748678}
	.design-toggle:hover,.design-toggle:focus-visible{background:#183d2d;color:#fff;outline-offset:2px}
	.design-toggle:hover .label,.design-toggle:focus-visible .label{color:#b9cabb}
</style>
