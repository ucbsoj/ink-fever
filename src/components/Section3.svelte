
<script>
    import Skull from "$components/Skull.svelte";

	let buttons = [
		{text: "A", left: "50%", top: "50%"},
		{text: "B", left: "47%", top: "10%"},
		{text: "C", left: "70%", top: "21%"},
		{text: "D", left: "42%", top: "80%"}
	]
	let buttonPressed = $state(undefined);

	const onClick = (buttonId) => {
		buttonPressed = buttonId;
	}

	const close = () => {
		buttonPressed = undefined;
	}

	$inspect({buttonPressed})
</script>
<div class="end">



<div class="body-map">
	{#each buttons as button}
		<button class="tattoo" style:left={button.left} style:top={button.top} onclick={() => onClick(button.text)}>
			<img src="assets/images/icon3.png"/>
             
		</button>
	{/each}
</div>

<div class="popup" class:visible={buttonPressed !== undefined}>
		{#if buttonPressed === "A"}
			<Skull />
		{:else if buttonPressed === "B"}
			<p>This is the B content</p>
		{:else}
			<p>You clicked something other than A or B!</p>
		{/if}

	<button class="close" onclick={close}>x</button>
</div>


</div>
<!-- closed .end -->

<style>
	.popup {
		background: #faefe0;
		height: 400px;
		width: 400px;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		visibility: hidden;
		padding: 2rem;
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
		background: #F9E4C6;
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
        background-image: url("assets/images/tattoomap.png");
        background-size: contain;
        background-position: center;
        background-repeat: no-repeat;
        
    }

</style>
