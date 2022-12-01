<script lang="ts">
	import EditCommentForm from "./editCommentForm.svelte";
  import type { Comments } from "src/types/Comments";

  let editComment: boolean = false;
  
  let id: number;
  let last_modification: string;
  let text: string;

  let comments: Comments[];

  function toggleEditComment() {
    editComment = !editComment;
  }

  const deleteComment = async (): Promise<string> => {
    const response = await fetch(`http://127.0.0.1:8000/comments/${id}`, {
      method: 'DELETE'
    })
  
    comments = comments.filter((array) => {
      return array[0] != id
    })

    const data = await response.json()
    return data
  }

  export { id, text, last_modification, comments };
</script>

<div class="flex flex-col mb-5">
  <p class="text-sm text-gray-600 mb-1">
    <span>user</span> |
    <button class="underline hover:text-gray-800" on:click={toggleEditComment}>edit</button>,
    <button class="underline hover:text-gray-800" on:click={deleteComment}>delete</button> |
    <span>{ last_modification }</span>
  </p>
  {#if editComment}
    <EditCommentForm bind:text={ text } commentId={ id } toggleEdit={ toggleEditComment }/>
  {:else}
    <p>
      { text }
    </p>
  {/if}
</div>
