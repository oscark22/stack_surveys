<script lang="ts">
	import CreateCommentForm from "./createCommentForm.svelte";
  import type { Comments } from "src/types/Comments";
  
  let addComment: boolean = true;
  let comments: Comments[];

  function toggleAddComment() {
    addComment = !addComment;
  }

  export { comments }
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
    <CreateCommentForm bind:comments={comments}/>
  {/if}
</div>
