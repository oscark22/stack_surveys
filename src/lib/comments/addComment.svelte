<script lang="ts">
	import CreateCommentForm from "./createCommentForm.svelte";
  
  let addComment: boolean = true;

  function toggleAddComment() {
    addComment = !addComment;
  }
</script>

<div class="flex-1 flex-col mb-6">
  <div class="flex">
    <button on:click={toggleAddComment} class="hover:text-blue-600">
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
    <CreateCommentForm />
  {/if}
</div>
