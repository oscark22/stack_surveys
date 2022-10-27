<script lang="ts">
  import BlueButton from "./blueButton.svelte";
  import TextArea from "./textArea.svelte";

  export let placeholderText: string;
</script>

<TextArea placeholderText={placeholderText} />
<div class="flex gap-2">
  <BlueButton text="Confirm" />
  <BlueButton text="Cancel" />
</div>
