<script lang="ts">
  import CommentTextArea from './commentTextArea.svelte'

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
    <CommentTextArea buttonText="Create" />
  {/if}
</div>