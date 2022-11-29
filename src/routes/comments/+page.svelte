<script lang="ts">
  import Title from '$lib/title.svelte';
  import CommentList from '$lib/comments/commentList.svelte';
  import AddComment from '$lib/comments/addComment.svelte'
	import Comment from '$lib/comments/comment.svelte';
</script>

<Title 
  title="Comments"
  subtitle="This is a comments section. Feel free to share your thoughts!"
/>
<div>
  <AddComment />
  <CommentList />
</div>
