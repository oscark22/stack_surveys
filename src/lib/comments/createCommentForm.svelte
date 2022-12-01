<script lang="ts">
  import BlueButton from "../blueButton.svelte";
  import TextArea from "../textArea.svelte";

  let commentInformation = '';

  type Comments = [number, string, string]
  let comments: Comments[];

  const createComment = async (): Promise<void> => {
    const comment = {
      user_id: "id1",
      text: commentInformation
    }

    const response = await fetch("http://127.0.0.1:8000/comments", {
      method: 'POST',
      headers: {'Content-Type': 'application/json'},
      body: JSON.stringify(comment)
    })

    const data = await response.json();
    comments = [data, ...comments]
  }

  export { comments }
</script>

<TextArea bind:text={commentInformation} />
<div class="flex">
  <BlueButton text="Create" someFunction={createComment} />
</div>
