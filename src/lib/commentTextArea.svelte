<script lang="ts">
  let placeholderText: string = "Insert you comment here";
  let buttonText: string;

  export { placeholderText, buttonText }
</script>

<div class="flex mt-3 mb-3">
  <textarea class="block w-full p-4 rounded-md border" placeholder={placeholderText} />
</div>
<div class="flex">
  <button class="py-2 px-8 bg-blue-50 rounded-md text-blue-600 hover:bg-blue-100">
    {buttonText}
  </button>
</div>
