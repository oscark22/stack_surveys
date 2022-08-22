<script lang="ts">
  let title: string = 'undefined';
  let from_color: string;
  let to_color: string;

  export { title, from_color, to_color };
</script>

<div class="flex-1">
  <div class="py-4 lg:px-8 rounded-md bg-gradient-to-r {from_color} {to_color}">
    <h1 class="text-center font-bold lg:text-3xl">
      { title }
    </h1>
  </div>
</div>