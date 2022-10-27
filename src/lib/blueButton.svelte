<script lang="ts">
  let text: string;
  let someFunction: () => void;

  export { text, someFunction }
</script>

<button on:click={someFunction} class="py-2 px-8 bg-blue-50 rounded-md text-blue-600 hover:bg-blue-100">
  {text}
</button>
