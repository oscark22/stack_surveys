<script lang="ts">
  import BlueButton from "./blueButton.svelte";
  import TextArea from "./textArea.svelte";

  let myFunction = (): void => {
    alert("Salutes from createCommentForm");
  }
</script>

<TextArea placeholderText="Insert your comment here." />
<div class="flex">
  <BlueButton text="Create" someFunction={myFunction} />
</div>

