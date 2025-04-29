<script>
	import Demo from "$components/demo/Demo.svelte";
	import Footer from "$components/Footer.svelte";
	import Hero from "$components/helpers/Hero.svelte";
	import Section1 from "$components/Section1.svelte";
	import Section2 from "$components/Section2.svelte";
	import Section3 from "$components/Section3.svelte";



</script>

<Hero 

hed="Ink Fever"
dek="What the #$%! is going on with tattoos?"
byline="From Young Squad"
src="assets/images/hero.mp4"
alt="A lake and some clouds"

/>


<Section1 />

<Section1 />

<Section1 />

<Section2 /> 

<Section3 />

<!-- <Section4 /> -->








<Footer />

<style>
	:global(body) {
		background-color: #F8e3BC;
		color: #1D201F;
		background-image: url("assets/images/backdrop.jpg");
		cursor: url("assets/images/tatgun2.png"), auto;
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