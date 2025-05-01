<script>
    import { fade } from 'svelte/transition';
    
    let isDrawing = false;
    let paths = [];
    let currentPath = [];

    function handleMouseDown(event) {
        console.log("Mouse down at:", event.clientX, event.clientY);
        isDrawing = true;
        currentPath = [[event.clientX, event.clientY]];
    }

    function handleMouseMove(event) {
        if (!isDrawing) return;
        console.log("Mouse move at:", event.clientX, event.clientY);
        currentPath = [...currentPath, [event.clientX, event.clientY]];
    }

    function handleMouseUp() {
        if (!isDrawing) return;
        console.log("Mouse up, path completed:", currentPath);
        isDrawing = false;
        paths = [...paths, currentPath];
        let pathJustAdded = currentPath;
        currentPath = [];
        
        // Remove the path after 5 seconds
        setTimeout(() => {
            console.log("Removing path:", pathJustAdded);
            paths = paths.filter(d => !arraysEqual(d, pathJustAdded));
        }, 5000);
    }

    function toSVGPath(points) {
        if (points.length === 0) return "";
        const [start, ...rest] = points;
        const path = `M${start[0]},${start[1]} ` + rest.map(([x, y]) => `L${x},${y}`).join(" ");
        console.log("Generated SVG Path:", path);
        return path;
    }

    function arraysEqual(a, b) {
        if (a.length !== b.length) return false;
        return a.every(([x1, y1], i) => {
            const [x2, y2] = b[i];
            return x1 === x2 && y1 === y2;
        });
    }
</script>

<div class="canvas"
    on:mousedown={handleMouseDown}
    on:mousemove={handleMouseMove}
    on:mouseup={handleMouseUp}>
    
    <svg>
        {#each paths as path (path.join("-"))}
            <path d={toSVGPath(path)} fill="none" stroke="black" stroke-width="2" out:fade />
        {/each}
        {#if isDrawing}
            <path d={toSVGPath(currentPath)} fill="none" stroke="purple" stroke-width="2" />
        {/if}
    </svg>
</div>

<style>
    .canvas {
        height: 100vh;
        width: 100vw;
        position: fixed;
        top: 0;
        z-index: 1;
        background-color: rgba(255, 0, 0, 0.1); /* Debugging */
    }

    svg {
        width: 100%;
        height: 100%;
    }
</style>