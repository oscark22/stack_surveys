<script>
  import "../app.css";
  import Navbar from '$lib/navbar.svelte';
</script>

<div class="sticky flex justify-center py-3 border-b border-gray-300">
  <img src="placeholder.png" alt="placeholder">
</div>
<body>
  <div class="w-full">
    <div class="flex-1">
      <div class="h-full">
        <div class="flex">
          <Navbar />
          <slot />
        </div>
      </div>
    </div>
  </div>
</body>
