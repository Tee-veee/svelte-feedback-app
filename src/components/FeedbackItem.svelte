<script>
  import { createEventDispatcher } from "svelte";
  import Card from "./UI/Card.svelte";
  export let item;

  const dispatch = createEventDispatcher();

  const handleDelete = (itemID) => {
    dispatch("delete-feedback", itemID);
  };
</script>

<Card>
  <div class="num-display">{item.rating}</div>
  <button class="close" on:click={() => handleDelete(item.id)}>X</button>
  <p class="text-display">
    {item.text}
  </p>
</Card>

<style>
  .num-display {
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: -10px;
    left: -10px;
    height: 50px;
    width: 50px;
    background-color: rgb(0, 218, 65);
    color: white;
    border: 1px solid white;
    border-radius: 50%;
    padding: 10px;
    font-size: 16px;
  }

  .close {
    position: absolute;
    top: 10px;
    right: 10px;
    background: none;
    border: none;
  }
</style>
