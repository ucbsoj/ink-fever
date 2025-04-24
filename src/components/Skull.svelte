<script>
    import Image from "$components/helpers/Image.svelte";
</script>

<p> Here is content!</p>

<div class="small">
    <Image
        src="assets/images/splat.png"
        alt="A lake and some clouds"
        caption="Me getting inked up!"
    />
</div>


<style>
    .small {
		width: 300px;
		margin: 36px auto;
	}
</style>