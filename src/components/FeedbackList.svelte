<script>
  import FeedbackItem from "./FeedbackItem.svelte";
  export let feedback = [];
</script>

{#each feedback as feedbk (feedbk.id)}
  <FeedbackItem item={feedbk} on:delete-feedback />
{/each}
