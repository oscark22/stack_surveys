<script lang="ts">
	import Comment from "./comment.svelte";
  import BlueButton from "../blueButton.svelte";
  import TextArea from "../textArea.svelte";

  let commentInformation = '';

  const createComment = async (): Promise<String> => {
    const comment = {
      user_id: 1,
      text: commentInformation
    }

    console.log(JSON.stringify(commentInformation))
    const response = await fetch("/comments", {
      method: 'POST',
      body: JSON.stringify(comment)
    })
    return response.json();
  }
</script>

<TextArea bind:text={commentInformation} />
<div class="flex">
  <BlueButton text="Create" someFunction={createComment} />
</div>
