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
	aria-label="gallery-thumbnails"
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
		class="gallery-thumbnails-icon"
		class:animate={isHovered}
	>
		<rect width="18" height="14" x="3" y="3" rx="2" />
		{#each ['M4 21h1', 'M9 21h1', 'M14 21h1', 'M19 21h1'] as d, index}
			<path {d} class="thumbnail-line" style="--index: {index + 1}" />
		{/each}
	</svg>
</div>

<style>
	.gallery-thumbnails-icon {
		overflow: visible;
	}

	.thumbnail-line {
		opacity: 1;
		transition: opacity 0.2s ease;
	}

	.gallery-thumbnails-icon.animate .thumbnail-line {
		opacity: 0;
		animation: fadeInSequence 0.3s ease forwards;
		animation-delay: calc(0.1s + var(--index) * 0.15s);
	}

	@keyframes fadeInSequence {
		0% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
</style>
