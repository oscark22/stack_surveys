<script lang="ts">
import { onMount } from "svelte";
import AddComment from "./addComment.svelte";
import Comment from "./comment.svelte";

type Comments = [number, string, string]
let comments: Comments[] = [];
  
onMount(async () => {
  const response = await fetch('http://127.0.0.1:8000/comments')
  comments = await response.json()
})

export { comments }
</script>


<AddComment bind:comments={comments} />
{#each comments as comment }
  <Comment
    id={ comment[0] }
    text={ comment[1] }
    last_modification={ `${comment[2].slice(0, 10)} ${comment[2].slice(11, 19)}` }
  />
{/each}
