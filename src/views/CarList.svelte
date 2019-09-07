<script>
  import { onMount } from "svelte";
  import CarListItem from "./CarListItem.svelte";

  let cars = [];

  function deleteItem(event) {
    cars = cars.filter(car => {
      return car.id !== event.detail.id;
    });
  }

  function getCars() {
    cars = [
      {
        id: 0,
        brand: "Hyundai",
        plate: "PHP-0909"
      },
      {
        id: 1,
        brand: "FIAT",
        plate: "AAW-7788"
      }
    ];
  }

  onMount(getCars);
</script>

<div id="car-list">
  <h1>Lista de veículos</h1>

  {#each cars as car}
    <CarListItem {...car} on:remove={deleteItem} />
  {/each}
</div>
