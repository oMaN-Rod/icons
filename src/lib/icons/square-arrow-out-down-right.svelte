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
	}

	function handleMouseLeave() {
		isHovered = false;
	}
</script>

<div
	class={classes}
	aria-label="square-arrow-out-down-right"
	role="img"
	onmouseenter={handleMouseEnter}
	onmouseleave={handleMouseLeave}
>
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
		<path d="M21 11V5a2 2 0 0 0-2-2H5a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h6" />
		<g class="arrow" class:animate={isHovered}>
			<path d="m21 21-9-9" />
			<path d="M21 15v6h-6" />
		</g>
	</svg>
</div>

<style>
	.arrow path {
		transition: transform 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
	}
	.animate {
		animation: moveDownRight 0.5s;
	}
	@keyframes moveDownRight {
		0%,
		100% {
			transform: translate(0, 0);
		}
		50% {
			transform: translate(-2px, -2px);
		}
	}
</style>
