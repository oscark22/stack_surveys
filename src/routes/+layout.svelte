<script>
  import "../app.css";
  import Navbar from '$lib/navbar.svelte';
</script>

<div class="sticky flex justify-center p-3 border-b border-gray-300">
  <img src="placeholder.png" alt="placeholder">
</div>
<body>
  <div class="w-full">
    <div class="flex-1">
      <div class="h-full">
        <div class="flex">
          <Navbar />
          <div class="flex-1">
            <div class="h-full p-4 lg:p-6">
              <div class="flex-1 h-full">
                <slot />
              </div>
            </div>
          </div>          
        </div>
      </div>
    </div>
  </div>
</body>
