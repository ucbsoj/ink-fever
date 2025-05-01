<script>
    import Image from "$components/helpers/Image.svelte";
    import painfront from "$svg/painfront.svg";

    
    // const onHover = (buttonId) => {
	// 	buttonPressed = buttonId;
	// }

    // $effect(() => {
	
    //     // get all paths in the Svg and run onHover when hovered
    //     const paths = document.querySelectorAll("path");
    //     paths.forEach((path) => {
    //         path.addEventListener("mouseover", () => {
    //             const buttonId = path.id;
    //             onHover(buttonId);
    //         });
    //     });
        

	// 	// const rects = document.querySelectorAll("rect");
	// 	// rects.forEach((rect) => {
	// 	// 	rect.addEventListener("click", () => {
	// 	// 		const buttonId = rect.id;
	// 	// 		onClick(buttonId);
			
	// 	// 	});
	// 	// });
	// });

   


</script>

<div class="full">

<div class="scroll">

    <h1>Hover on the body part to see the PAIN!!!</h1>
    
    <div class="pain">
        {@html painfront}
        </div>


</div>

</div>

<!-- close .full -->

<style>

    h1 {
        font-family: "Rock";
        font-size: 1rem;
        text-align: center;
        margin-top: 20px;
    }
    .small {
		width: 300px;
		margin: 36px auto;
	}

    .scroll{
        width: 100%;
        position: absolute;
        overflow: scroll;
    }

    .pain {
        position: relative;
        width: 40%;
        height: 60%;
    }
    .full {
        width: 100%;
        height: 100%;
        background-color: #faefe0;
        position: relative;
        overflow: scroll;
    }

    /* path:hover {
        fill: #faefe0;
        cursor: pointer;
    } */

    :global(.pain #leg:hover) {
        fill: orange;
        cursor: pointer;
    }

    :global(.pain #legs:hover) {
        fill: orange;
        cursor: pointer;
    }

    :global(.pain #torso:hover) {
        fill: rgb(69, 173, 229);
        cursor: pointer;
    }

    :global(.pain #arm:hover) {
        fill: rgb(249, 209, 33);
        cursor: pointer;
    }

    :global(.pain #face:hover) {
        fill: red;
        cursor: pointer;
    }

</style>