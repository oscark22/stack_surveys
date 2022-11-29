<script lang="ts">
	import EditCommentForm from "./editCommentForm.svelte";

  let editComment: boolean = false;
  let last_modification: string;
  let text: string;

  function toggleEditComment() {
    editComment = !editComment;
  }

  export { text, last_modification };
</script>

<div class="flex flex-col mb-5">
  <p class="text-sm text-gray-600 mb-1">
    <span>user</span> |
    <button class="underline hover:text-gray-800" on:click={toggleEditComment}>edit</button>,
    <button class="underline hover:text-gray-800">delete</button> |
    <span>{ last_modification }</span>
  </p>
  {#if editComment}
    <EditCommentForm placeholderText={ text } />
  {:else}
    <p>
      { text }
    </p>
  {/if}
</div>
