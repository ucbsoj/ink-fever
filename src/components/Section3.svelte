
<script>
    import Skull from "$components/Skull.svelte";
	import bodySvg from "$svg/body1.svg";
	import Spider from "$components/Spider.svelte";
	import Heart from "$components/Heart.svelte";
	import tatkey from "$svg/tatkey.svg";
	import Bird from "$components/Bird.svelte";

	// let buttons = [
	// 	{text: "A", left: "50%", top: "50%"},
	// 	{text: "B", left: "47%", top: "10%"},
	// 	{text: "C", left: "70%", top: "21%"},
	// 	{text: "D", left: "42%", top: "80%"}
	// ]
	let buttonPressed = $state(undefined);

	const onClick = (buttonId) => {
		buttonPressed = buttonId;
	}

	const close = () => {
		buttonPressed = undefined;
	}

	$effect(() => {
		// Get all the elipses in the SVG and run onclick when clicked
		// const elipses = document.querySelectorAll("ellipse");
		// elipses.forEach((ellipse) => {
		// 	ellipse.addEventListener("click", () => {
		// 		const buttonId = ellipse.id;
		// 		onClick(buttonId);

		// get all rect in the SVG and run onclick when clicked
		const rects = document.querySelectorAll("rect");
		rects.forEach((rect) => {
			rect.addEventListener("click", () => {
				const buttonId = rect.id;
				onClick(buttonId);
			
			});
		});
	});

	$inspect(buttonPressed)
</script>

<!-- <div class="end"> -->



<!-- <div class="body-map">
	{#each buttons as button}
		<button class="tattoo" style:left={button.left} style:top={button.top} onclick={() => onClick(button.text)}>
			<img src="assets/images/icon3.png"/>
				
		</button>
	{/each}
</div> -->


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
			<p>This is a modern history of Tattoos</p>
		{:else if buttonPressed === "heart"}
			<Heart />
		{:else if buttonPressed === "flower"}
			<p>This is a flower.</p>
		{:else if buttonPressed === "bird"}
			<Bird />
		{:else if buttonPressed === "hand"}
			<p>This is a hand.</p>
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
