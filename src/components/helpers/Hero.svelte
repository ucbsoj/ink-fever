<script>
	const { hed, dek, byline, src, alt } = $props();
</script>

<div class="hero">
	{#if src.endsWith(".mp4")}
		<video {src} autoplay loop muted playsinline></video>
	{:else}
		<img {src} {alt} />
	{/if}

	<!-- co pilot and ask for it to be in a container with a background. png or svg image ink splatters -->
	<div class="text">
		{#if dek}<h2>{@html dek}</h2>{/if}
		{#if byline}<p>{@html byline}</p>{/if}

	</div>

	<div class="text2">
		{#if hed}<h1>{@html hed}</h1>{/if}
	</div>
</div>

<style>
	.hero {
		width: 100vw;
		height: 100vh;
		position: relative;
	}

	img,
	video {
		height: 100%;
		width: 100%;
		object-fit: cover;
	}

	.text {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-5%, -50%);
		color: #1D201F;
		background: #F8e3BC;
		padding: 0 1.5rem;
		text-align: center;
		border-radius: 90px;
		font-weight: bolder;
		background-image: url("assets/images/backdrop.jpg");
		font-family: "Sailor";
	}

	.text2 {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-105%, -250%);
		color: #1D201F;
		background: #F8e3BC;
		padding: 0 1rem;
		text-align: center;
		border-radius: 100px;
		font-family: "Sailor";
		background-image: url("assets/images/backdrop.jpg");
	}
	/* in the test section you would specify */

</style>
