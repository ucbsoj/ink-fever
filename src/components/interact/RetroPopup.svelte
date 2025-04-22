<script>
    import { onMount, onDestroy } from 'svelte';
    const { title = 'Retro Window', visible: visibleProp = true } = $props();
    let visible = visibleProp;
  
    let pos = { x: 100, y: 100 };
    let offset = { x: 0, y: 0 };
    let isDragging = false;
    let z = 10;
  
    function close() {
      visible = false;
    }
  
    function startDrag(e) {
      isDragging = true;
      offset.x = e.clientX - pos.x;
      offset.y = e.clientY - pos.y;
      z += 1;
    }
  
    function onDrag(e) {
      if (!isDragging) return;
      pos.x = e.clientX - offset.x;
      pos.y = e.clientY - offset.y;
    }
  
    function stopDrag() {
      isDragging = false;
    }
  
    // 🧠 hook into window events
    onMount(() => {
      window.addEventListener('mousemove', onDrag);
      window.addEventListener('mouseup', stopDrag);
  
      return () => {
        window.removeEventListener('mousemove', onDrag);
        window.removeEventListener('mouseup', stopDrag);
      };
    });
  </script>
  