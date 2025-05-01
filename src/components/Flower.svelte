<script>
	import { onMount } from 'svelte';

	let videoElement;
	let playButtonElement;
	let isPlaying = $state(false);

	onMount(() => {
		// Start paused
		videoElement.pause();

		// Keep text updated if user plays/pauses directly
		videoElement.addEventListener('play', () => {
			isPlaying = true;
		});
		videoElement.addEventListener('pause', () => {
			isPlaying = false;
		});
	});

	function togglePlay() {
		if (videoElement.paused) {
			videoElement.play();
		} else {
			videoElement.pause();
		}
	}
</script>

<div class="vid">
	<video
		bind:this={videoElement}
		src="assets/images/hero.mp4"
		loop
		muted
	></video>

	<button
		class="play-button"
		bind:this={playButtonElement}
		on:click={togglePlay}
	>
		{isPlaying ? 'Pause Video' : 'Play Video'}
	</button>
</div>

<style>
	.vid {
		position: relative;
		width: 100%;
		height: 100%;
		overflow: hidden;
	}

	video {
        position: relative;
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.play-button {
		position: absolute;
		top: 20px;
		left: 20px;
		z-index: 10;
		background-color: rgba(255, 255, 255, 0.85);
		border: none;
		padding: 12px 20px;
		font-size: 1rem;
		cursor: pointer;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
	}
</style>
