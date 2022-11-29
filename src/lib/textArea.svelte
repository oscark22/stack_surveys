<script lang="ts">
  let placeholderText = "Insert you comment here.";
  let text: string;

  export { placeholderText, text };
</script>

<div class="flex mt-3 mb-3">
  <textarea bind:value={text} class="block w-full p-4 rounded-md border" placeholder={placeholderText} />
</div>
