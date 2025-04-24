<script>
    const showPopup = $state(true);

    import { onMount} from 'svelte';
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
  
  <!-- ✅ Runes prefers `onclick` -->
  <button onclick={() => showPopup.set(true)}>Open Popup</button>
  
  <RetroPopup
    title="My Retro Box"
    visible={showPopup()}
    onclose={() => showPopup.set(false)}
  >
    <img src="https://placekitten.com/200/150" alt="Kitten" />
    <p>Look at this retro cat 🐱✨</p>
  </RetroPopup>
  
  