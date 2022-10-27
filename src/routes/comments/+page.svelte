<script lang="ts">
  import Title from '$lib/title.svelte';
  import Comment from '$lib/comment.svelte';
  import AddComment from '$lib/addComment.svelte'
</script>

<Title 
  title="Comments"
  subtitle="This is a comments section. Feel free to share your thoughts!"
/>
<div>
  <AddComment />
  <Comment placeholderText="something" />
</div>
