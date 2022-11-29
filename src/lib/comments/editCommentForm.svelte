<script lang="ts">
  import BlueButton from "../blueButton.svelte";
  import TextArea from "../textArea.svelte";

  let text = '';
  let commentId: number;
  let toggleEdit: () => void;

  const updateComment = async (): Promise<string> => {
    const comment = {
      user_id: "id1",
      text: text
    }

    const response = await fetch(`http://127.0.0.1:8000/comments/${commentId}`, {
      method: 'PUT',
      headers: {'Content-Type': 'application/json'},
      body: JSON.stringify(comment)
    })
    const data = await response.json()
    return data
  }

  export { text, commentId, toggleEdit }
</script>

<TextArea bind:text={text} />
<div class="flex gap-2">
  <BlueButton text="Confirm" someFunction={updateComment} />
  <BlueButton text="Cancel" someFunction={toggleEdit} />
</div>
