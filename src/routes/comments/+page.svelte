<script lang="ts">
  import Title from '$lib/title.svelte';
  import CommentList from '$lib/comments/commentList.svelte';
</script>

<Title 
  title="Comments"
  subtitle="This is a comments section. Feel free to share your thoughts!"
/>
<div>
  <CommentList />
</div>
