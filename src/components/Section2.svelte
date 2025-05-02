<script>
    import Image from "$components/helpers/Image.svelte";
    import draw from "$svg/draw.svg"

</script>

<div class="sec">
    <div class="full">
       <div class="center">
        <h1> Observe the illustrated humanoid:</h1>
   

         <h1>Listen to their heart...</h1>

        </div>

    <!-- <div class="small">
	    <Image
		    src="assets/images/body-topper.png"
		    alt="A lake and some clouds"
		    caption="The image will fill the width and height of its container"
	    />
    </div> -->


    <!-- <div class="draw">
        {@html draw}
    </div> -->

    </div>   
    
</div>






<style>
   
   .full {
        width: 100%;
        height: 100%;
        position: relative;
        padding: 10px;
        
    }

    
	.small {
		width: 300px;
		margin: 36px auto;
	}

    .sec {
        width: 100%;
        height: 100%;
        margin: 20px auto;
        padding: 10px;
        border-radius: 10px;
    
    }
    
    h1 {
    font-weight: bold;
    font-family: "Rock";
    letter-spacing: 0.5rem;
    color: #983628;
    text-align: center;
    
    }

    /* .draw {	
		position: absolute;
		top: -1vh;
		right: 1vw;
		background: transparent;
		width: 35%;
		height: 75%;
		z-index: -1;
        

	} */
/* 
    .center {
        position: relative;
        margin-left: auto;
        margin-right: auto;
        width: 50%; 
        
       
    } */

    
    </style>