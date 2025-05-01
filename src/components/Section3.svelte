
<script>
    import Skull from "$components/Skull.svelte";
	import bodySvg from "$svg/body1.svg";
	import Spider from "$components/Spider.svelte";
	import Heart from "$components/Heart.svelte";
	import tatkey from "$svg/tatkey.svg";
	import Bird from "$components/Bird.svelte";
	import Ball from "$components/Ball.svelte";
	import Hand from "$components/Hand.svelte";
	import Flower from "$components/Flower.svelte";


	let buttonPressed = $state(undefined);


	const close = () => {
		buttonPressed = undefined;
	}

	$effect(() => {
		
		// get all rect in the SVG and run onclick when clicked
		const rects = document.querySelectorAll("rect");
		rects.forEach((rect) => {
			if (rect.id === "heart") {
				rect.classList.add("pulse");
			};
			
			rect.addEventListener("click", () => {
				const buttonId = rect.id;
				buttonPressed = buttonId;
				// remove class pulse from heart (alt)
				// rects.forEach((r) => {
				// 	if (r.id === "heart") {
				// 		r.classList.remove("pulse");
				// 	}
				// });
				
				const heart = Array.from(rects).find((r) => r.id === "heart");
				heart.classList.remove("pulse");
				
			});
		});
	});

	$inspect(buttonPressed)
</script>



<div class="end">
	<div class="key">
		{@html tatkey}
	</div>
	<div class="bodSvg">
		{@html bodySvg}
	</div>



	<div class="popup" class:visible={buttonPressed !== undefined}>
		{#if buttonPressed === "skull"}
			<Skull />
		{:else if buttonPressed === "ball"}
			<Ball />
		{:else if buttonPressed === "heart"}
			<Heart />
		{:else if buttonPressed === "flower"}
			<Flower />
		{:else if buttonPressed === "bird"}
			<Bird />
		{:else if buttonPressed === "hand"}
			<Hand />
		{:else if buttonPressed === "spider"}
			<Spider />
		
		{:else}
			<p>You clicked something other than A or B!</p>
		{/if}

		<button class="close" onclick={close}>x</button>
	</div>

</div>

<!-- </div> -->
<!-- closed .end -->

<style>
	.popup {
		background: #faefe0;
		height: 60vh;
		width: 60vw;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		visibility: hidden;
		padding: 2rem;
		z-index: 4;
	}

	:global(#heart.pulse) {
		animation: pulse 1.8s infinite;
		transform-box: fill-box;
		transform-origin: center !important;

	}

	@keyframes pulse {
		0% {
			transform: scale(1);
		}
		50% {
			transform: scale(1.3);
		}
		100% {
			transform: scale(1);
		}
	}

	:global(.bodSvg rect:hover){
		cursor: pointer;
		transform: scale(1.15);
		transform-box: fill-box;
		transform-origin: center !important;
		transition: transform 0.2s;
		
	}

	.popup.visible {
		visibility: visible;
	}
	
	.body-map {
		position: relative;
		background: transparent;
		height: 100vh;
		width: 100vw;
	}

	button.tattoo {
		position: absolute;
		border: grey;
		background:transparent;
        width: 50px;
        height: 50px;
        border-radius: 50%;
	}

	button.close {
		position: absolute;
        top: 0;
        left: 0;
        background: rgb(231, 95, 95);
	}
	
    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .end { 
        height: 100vh;
        width: 100vw;
        position: relative;
        /* background-image: url("assets/images/tattoomap.png"); */
        background-size: contain;
        background-position: center;
        background-repeat: no-repeat;
		margin: 5px, 10px;
		padding: 2px, 2px;
		justify-content: center;
        
    }

	.bodSvg {
		width: 400px;
		height: 900px;
		position: relative;
		background: transparent;
		top: 50vh;
		left: 50vw;
		transform: translate(-50%, -50%);
		padding: 2rem;
		z-index: 3;
		
	}
		
	.key {	
		position: absolute;
		top: 20vh;
		left: 5vw;
		background: transparent;
		width: 30%;
		height: 60%;
		z-index: -1;

	}

</style>
