<script>
  import { createEventDispatcher } from "svelte";

  export let id;
  export let brand;
  export let plate;

  const dispatch = createEventDispatcher();

  function remove() {
      dispatch('remove', {id: id})
  }
</script>

<div class="car-list-item">
  <h3>
    {brand}
    <small>{plate}</small>
  </h3>

  <button class="black" on:click={remove}>Remove</button>
</div>
