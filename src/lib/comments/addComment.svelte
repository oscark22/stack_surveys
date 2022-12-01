<script lang="ts">
	import Comment from "./comment.svelte";
	import CreateCommentForm from "./createCommentForm.svelte";
  
  let addComment: boolean = true;
  
  type Comments = [number, string, string]
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
