<script>
    import {base} from '$app/paths';
</script>
<div class="full">
    <!-- <div>
        <img src="assets/images/ex2.png" alt="Background Image" />
    </div> -->


    <div class="scroll">
        <div>
            <img src="assets/images/art51.png" alt="Background Image" />
            <img src="assets/images/art52.png" alt="Background Image" />
            <img src="assets/images/art53.png" alt="Background Image" />
            <img src="assets/images/art54.png" alt="Background Image" />
            
        </div>
        <div class="link" style:background-image={`url('${base}/assets/images/art73.png')`}>
            <p>Go check out Edith at <a href="https://www.dailycal.org/archives/how-young-people-are-embracing-tattoos-with-open-arms/article_1ff01e28-98c5-5953-8cf4-25b40c6631e2.html">the Daily Cal</a>! But make sure to hit the browser back arrow to come back here after you're done! Don't get lost out there Silly.</p>
        </div>
    </div>
</div>


<style>
    .full {
        width: 100%;
        height: 100%;
        background-color: #faefe0;
        position: relative;
        overflow: scroll;
    }
    .scroll{
        width: 100%;
        position: relative;
        overflow: scroll;
    }
    .link {
        height: 40%;
        width: 100%;
        position: relative;
        padding-top: 10px;
        padding-right: 3px;
        padding-left: 3px;
        margin: 10px, 10px;
    }
</style>