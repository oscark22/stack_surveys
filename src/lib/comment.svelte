<script lang="ts">
  let editComment: boolean = false;

  function toggleEditComment() {
    editComment = !editComment;
  }
</script>

<div class="flex flex-col mb-5">
  <p class="text-sm text-gray-600 mb-1">
    <span>user</span> |
    <button class="underline hover:text-gray-800" on:click={toggleEditComment}>edit</button>,
    <button class="underline hover:text-gray-800">delete</button> |
    <span>2 minutes ago</span>
  </p>
  {#if editComment}
    here
  {:else}
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptates facere impedit perferendis ab tenetur, provident ipsum mollitia! Recusandae dolorum, unde rerum qui quod perferendis quam sapiente? Eius similique nobis obcaecati.
    </p>
  {/if}
</div>
