<script lang="ts">
  let addComment: boolean = true;

  function handleClick() {
    addComment = !addComment;
  }
</script>

<div class="flex-1 flex-col mb-6">
  <div class="flex">
    <button on:click={() => handleClick()} class="hover:text-blue-600">
      <span>
        {#if addComment}
          [-]
        {:else}
          [+]
        {/if}
      </span> 
      Add comment
    </button>
  </div>
  {#if addComment}
    <div class="flex mt-3 mb-3">
      <textarea class="block w-full p-4 rounded-md border" placeholder="Insert your comment here" />
    </div>
    <div class="flex">
      <button class="py-2 px-8 bg-blue-50 rounded-md text-blue-600 hover:bg-blue-100">
        Create
      </button>
    </div>
  {/if}
</div>