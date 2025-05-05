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
	
	<div class="top">
	<h1>Ancient Artist Alchemy</h1>	
	

	</div>
	<iframe width="100%" height="90%" src="https://www.youtube.com/embed/wLetVMqIUIc?si=r73cgkTb8jmw3X6s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
	<!-- <video
		bind:this={videoElement}
		src="assets/images/Finalmp4.mp4"
		loop
		
	></video> -->
 
<!-- <div class="bottom">
	<button
		class="play-button"
		bind:this={playButtonElement}
		on:click={togglePlay}
	>
		{isPlaying ? 'Pause' : 'Play'}
	</button>
</div> -->


<div class="down">
	<h1>Tattoo King Feo</h1>
	<p>San Francisco CA, born and raised artist.  
		Currently based out of Hidden Dragon Tattoo.
		Gnarly skills.</p>

	</div>
</div>




<style>
	.top {
		position: relative;
		width: 100%;
	}
	.vid {
		position: relative;
		width: 100%;
		height: 100%;
		overflow: scroll;
		
	}

	video {
        position: relative;
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.play-button {
		position: relative;
		top: 50%;
		left: 50%;
		z-index: 10;
		background-color: rgba(226, 236, 231, 0.85);
		color: #061413;
		border: black;
		border-width: 2px;
		border-style: solid;
		border-radius: 60rem;
		padding: 10px 5px;
		font-size: 1rem;
		cursor: pointer;
		box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.2);
		transform: scale(.9);
		transform-box: fill-box;
		transform-origin: center !important;
		transition: transform 0.2s;
		
		
	}

	.bottom{
		/* this div is below the video */
		position: relative;
		width: 100%;
		height: 2px;
		
	}

	.down {
		position: relative;
		width: 100%;
		overflow: scroll;
		margin-top: 15px;
		padding-top: 5px;
	}

	h1 {
		text-align: center;
		
	}
</style>
