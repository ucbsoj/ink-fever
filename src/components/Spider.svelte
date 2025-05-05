<script>

    import painfront from "$svg/painfront.svg";
    import painback from "$svg/painback.svg";

    
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

    <div>
        <img src="assets/images/art71.png" alt="Background Image" />
        <img src="assets/images/art72.png" alt="Background Image" />
  

        
    </div>


    <div class="sheet">
        
        <div class="pain">
            <h1>Hover on the body part to see the PAIN!!!</h1>
        {@html painfront}
       
        </div>
        <div class="painback">
            <h1>I'm a wuss so I pained it up from those other drawings!</h1>
            {@html painback}
            
            <div class="ow">
                <h1>OWWWW</h1>

            </div>
        </div>
    
    </div>
    <!-- close sheet -->
</div>

</div>

<!-- close .full -->

<style>

    .sheet{
        display: flex;
        width: 100%;
        height: 100%;
        position: relative;
        overflow: scroll;
        align-items: center;
        z-index: 1;
        background-image: url("../assets/images/art73.png");
    }

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
        width: 50%;
        height: 60%;
        display: inline-block;
        
    }

    .painback{
        position: relative;
        width: 50%;
        height: 60%;  
        display: inline-block; 
      
        
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
        fill: rgb(233, 139, 46);
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

    :global(.painback #back:hover) {
        fill: rgb(229, 224, 69);
        cursor: pointer;
      
    }

    :global(.painback #backarm:hover) {
        fill: rgb(69, 173, 229);
        cursor: pointer;
    }

    :global(.painback #backlegl:hover) {
        fill: rgb(99, 46, 233);
        cursor: pointer;
    }
    :global(.painback #backlegr:hover) {
        fill: rgb(99, 46, 233);
        cursor: pointer;
    }
    :global(.painback #backhead:hover) {
        fill: red;
        cursor: pointer;
    }
    :global(.painback #allback:hover) {
        fill: rgb(249, 33, 33);
        cursor: pointer;

    }

  


    

    /* .ow {
		background: #faefe0;
		height: 30%;
		width: 60%;
		position: relative;
		visibility: hidden;
		z-index: 6;
	} */

</style>