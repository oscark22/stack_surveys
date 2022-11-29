<script lang="ts">
import { onMount } from "svelte";
import Comment from "./comment.svelte";

export let comments: Array<Array<string>> = Array();
  
onMount(async () => {
  const response = await fetch('http://127.0.0.1:8000/comments')
  comments = await response.json()
  console.log(comments)
})
</script>

{#each comments as comment }
  <Comment
    text={ comment[0] }
    last_modification={ `${comment[1].slice(0, 10)} ${comment[1].slice(11, 19)}` }
  />
{/each}
