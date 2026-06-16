<script>
	import { onMount, onDestroy } from 'svelte';

	const projectUrl = 'https://github.com/ncntech/NasBeat';

	const achievements = [
		{ icon: 'fa-solid fa-star', label: 'Open Source', sub: 'Free forever' },
		{ icon: 'fa-solid fa-shield-halved', label: 'Privacy First', sub: 'No tracking' },
		{ icon: 'fa-solid fa-bolt', label: 'Rust-Powered', sub: 'Native performance' },
		{ icon: 'fa-solid fa-puzzle-piece', label: 'Plugin System', sub: 'Extensible by design' },
		{ icon: 'fa-solid fa-globe', label: 'Cross-Platform', sub: 'Android, Windows, Linux, macOS' },
		{ icon: 'fa-solid fa-music', label: 'Multi-Source', sub: 'All your music in one place' },
	];

	let rotation = 0;
	let autoRotateInterval;

	const numItems = achievements.length;
	const rotationAngle = 360 / numItems;

	let innerWidth = 0;
	let cardWidth = 190;
	let carouselRadius = 288;

	$: {
		if (innerWidth > 992) {
			cardWidth = 210;
		} else if (innerWidth > 600) {
			cardWidth = 190;
		} else {
			cardWidth = 150;
		}
		const angle = Math.PI / numItems;
		const gapFactor = 1.35;
		carouselRadius = (cardWidth / 2) * gapFactor / Math.tan(angle);
	}

	$: currentIndex = (Math.round((-rotation % 360) / rotationAngle) + numItems) % numItems;

	onMount(() => {
		autoRotateInterval = setInterval(() => {
			rotation -= rotationAngle;
		}, 3000);
	});

	onDestroy(() => {
		clearInterval(autoRotateInterval);
	});
</script>

<svelte:window bind:innerWidth />

<div
	class="awards-wrapper"
	aria-label="NasBeat achievements carousel"
	style="--radius: {carouselRadius}px; --card-width: {cardWidth}px;"
>
	<div class="awards-container">
		<div
			class="carousel"
			style="transform: translateZ(calc(var(--radius) * -1)) rotateY({rotation}deg);"
		>
			{#each achievements as item, i}
				<div
					class="carousel-item"
					class:active={i === currentIndex}
					style="transform: rotateY({i * rotationAngle}deg) translateZ(var(--radius));"
				>
					<a href={projectUrl} target="_blank" rel="noopener noreferrer" class="achievement-card">
						<i class="{item.icon} achievement-icon"></i>
						<span class="achievement-label">{item.label}</span>
						<span class="achievement-sub">{item.sub}</span>
					</a>
				</div>
			{/each}
		</div>
	</div>
</div>

<style>
	.awards-wrapper {
		width: 100%;
		max-width: 500px;
		margin: 1rem auto;
		padding: 0.5rem 0;
		display: flex;
		justify-content: center;
		position: relative;
		overflow: hidden;
	}

	.awards-container {
		width: 100%;
		height: 200px;
		position: relative;
		perspective: 1200px;
	}

	.carousel {
		width: 100%;
		height: 100%;
		position: absolute;
		transform-style: preserve-3d;
		transition: transform 1.2s cubic-bezier(0.77, 0, 0.175, 1);
	}

	.carousel-item {
		position: absolute;
		left: calc(50% - var(--card-width) / 2);
		top: 10px;
		width: var(--card-width);
		height: 180px;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 0.8rem;
		border-radius: 12px;
		box-sizing: border-box;
		background: rgba(30, 30, 45, 0.5);
		border: 1px solid rgba(255, 255, 255, 0.15);
		backdrop-filter: blur(10px);
		transition: transform 0.8s ease, opacity 0.8s ease;
		opacity: 0.5;
		transform-origin: center center;
	}

	.carousel-item.active {
		opacity: 1;
		transform: scale(1.1);
		border-color: rgba(255, 255, 255, 0.3);
	}

	.achievement-card {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 0.4rem;
		text-decoration: none;
		color: #fff;
		width: 100%;
		height: 100%;
	}

	.achievement-icon {
		font-size: 2rem;
		color: #e05c5c;
		text-shadow: 0 0 12px rgba(224, 92, 92, 0.5);
	}

	.achievement-label {
		font-size: 0.95rem;
		font-weight: 700;
		text-align: center;
		color: #fff;
	}

	.achievement-sub {
		font-size: 0.72rem;
		color: #aaa;
		text-align: center;
		line-height: 1.3;
	}

	@media (max-width: 992px) {
		.awards-wrapper { max-width: 400px; }
		.awards-container { height: 190px; }
	}

	@media (max-width: 600px) {
		.awards-wrapper { max-width: 320px; }
		.awards-container {
			height: 160px;
			perspective: 800px;
		}
		.carousel-item {
			height: 130px;
			top: 12px;
		}
		.achievement-icon { font-size: 1.6rem; }
	}
</style>
