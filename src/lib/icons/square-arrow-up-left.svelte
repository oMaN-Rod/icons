<script>
	let {
		color = 'currentColor',
		size = 28,
		strokeWidth = 2,
		isHovered = false,
		classes = ''
	} = $props();

	function handleMouseEnter() {
		isHovered = true;
		setTimeout(() => {
			isHovered = false;
		}, 200);
	}
</script>

<div class={classes} aria-label="square-arrow-up-left" role="img" onmouseenter={handleMouseEnter}>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		width={size}
		height={size}
		viewBox="0 0 24 24"
		fill="none"
		stroke={color}
		stroke-width={strokeWidth}
		stroke-linecap="round"
		stroke-linejoin="round"
	>
		<rect width="18" height="18" x="3" y="3" rx="2" />
		<path d="M8 16V8h8" class:head={isHovered} />
		<path d="M8 8 L12 12" class:head={isHovered} />
		<path d="M16 16 L12 12" />
	</svg>
</div>

<style>
	path {
		transition: all 0.2s ease-out;
	}
	.head {
		transform: translate(1.5px, 1.5px);
	}
</style>
