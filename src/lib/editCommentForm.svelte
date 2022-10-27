<script lang="ts">
  import BlueButton from "./blueButton.svelte";
  import TextArea from "./textArea.svelte";

  let someFunc = (): void => {
    alert("Salutes from editCommentForm");
  }

  export let placeholderText: string;
</script>

<TextArea placeholderText={placeholderText} />
<div class="flex gap-2">
  <BlueButton text="Confirm" someFunction={someFunc} />
  <BlueButton text="Cancel" someFunction={someFunc} />
</div>
