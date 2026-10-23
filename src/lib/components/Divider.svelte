<script lang="ts">
	// Adjustable variables
	let {
		startColor = '#0a0022cc',
		middleColor = '#00ffd2',
		endColor = '#0a0022cc',
		thickness = '2px'
	}: {
		startColor?: string;
		middleColor?: string;
		endColor?: string;
		thickness?: string;
	} = $props();
</script>

<hr
	class="divider"
	style:--gradient-start={startColor}
	style:--gradient-middle={middleColor}
	style:--gradient-end={endColor}
	style:--divider-thickness={thickness}
/>

<style>
	.divider {
		background: linear-gradient(
			90deg,
			var(--gradient-start),
			var(--gradient-middle),
			var(--gradient-end)
		);
		height: var(--divider-thickness);
		border: 0;
	}
</style>
