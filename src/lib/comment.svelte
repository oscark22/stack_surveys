<script lang="ts">
	import EditCommentForm from "./editCommentForm.svelte";

  let editComment: boolean = false;
  let placeholderText: string;

  function toggleEditComment() {
    editComment = !editComment;
  }

  export { placeholderText };
</script>

<div class="flex flex-col mb-5">
  <p class="text-sm text-gray-600 mb-1">
    <span>user</span> |
    <button class="underline hover:text-gray-800" on:click={toggleEditComment}>edit</button>,
    <button class="underline hover:text-gray-800">delete</button> |
    <span>2 minutes ago</span>
  </p>
  {#if editComment}
    <EditCommentForm placeholderText={placeholderText} />
  {:else}
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptates facere impedit perferendis ab tenetur, provident ipsum mollitia! Recusandae dolorum, unde rerum qui quod perferendis quam sapiente? Eius similique nobis obcaecati.
    </p>
  {/if}
</div>
