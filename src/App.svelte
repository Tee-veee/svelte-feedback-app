<script>
  import FeedbackList from "./components/FeedbackList.svelte";

  let feedback = [
    {
      id: 1,
      rating: 8,
      text: "ABC",
    },
    {
      id: 2,
      rating: 3,
      text: "ADHJSD",
    },
    {
      id: 3,
      rating: 6,
      text: "ASCLLSIL",
    },
    {
      id: 4,
      rating: 9,
      text: "FUJKFND",
    },
  ];

  $: count = feedback.length;

  const deleteFeedback = (e) => {
    const itemID = e.detail;
    feedback = feedback.filter((item) => item.id != itemID);
  };
</script>

<main class="container">
  <FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>

<style>
</style>
