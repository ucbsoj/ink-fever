<script>
	import Demo from "$components/demo/Demo.svelte";
	import Footer from "$components/Footer.svelte";
	import Hero from "$components/helpers/Hero.svelte";
	import Section1 from "$components/Section1.svelte";
	import Section2 from "$components/Section2.svelte";
	import Section3 from "$components/Section3.svelte";
	import Canvas from "$components/Canvas.svelte";
	import { base } from "$app/paths";

	$effect(() => {
		// set the body background image to the backdrop image
		const body = document.querySelector("body");
		body.style.backgroundImage = `url("${base}/assets/images/backdrop.jpg")`;

		// set the cursor image to the tattoo gun
		body.style.cursor = `url("${base}/assets/images/tatgun2.png") 16 16, auto`;
	})

</script>

<Hero 

hed="Ink Fever"
dek="What the #$%! is going on with tattoos?"
byline="From Young Squad"
src="assets/images/hero.mp4"
alt="A lake and some clouds"

/>


<Section1 />

<!-- <Section1 />

<Section1 /> -->

<Section2 /> 

<Section3 />

<!-- <Section4 /> -->

<Canvas />




<Footer />

<style>
	:global(body) {
		background-color: #F8e3BC;
		color: #1D201F;
	}
	
	:global(p) {
		font-family: "Type";
		font-size: 1.25rem;
		
	}

	:global(h1) {
		font-family: "Sailor";
		font-size: 2rem;
	}


	
</style>