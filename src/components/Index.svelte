<script>
	import Demo from "$components/demo/Demo.svelte";
	import Footer from "$components/Footer.svelte";
	import Hero from "$components/helpers/Hero.svelte";
	
	
	//import Section1 from "$components/Section1.svelte";
</script>

<Hero 

hed="Ink Fever"
dek="What the #$%! is going on with tattoos?"
byline="From Young Squad"
src="assets/images/hero.mp4"
alt="A lake and some clouds"

/>

<Demo />






<!-- <Section1 
title="My Retro Box"
visible={showPopup}
onclose={() => showPopup = false}
 />
 -->

<Footer />

<style>
	:global(body) {
		background-color: #F8e3BC;
		color: #1D201F;
	}
	
	:global(p) {
		font-family: "Patrick Hand";
	}

	:global(h1) {
		font-family: "Rock Salt";
	}
</style>