<script setup>
  let msg = "HOOOO";
</script>


<template>
  <div>
  <div class="todo">
    <h1>Voici la todo list </h1>
    <h1>CouCou55555</h1>
    <span>{{ msg }}</span>
    <h1>Salut</h1>
  </div>
  <label for="pet-select">Choose a pet:</label>

<select name="pets" id="pet-select">
    <option value="">--Please choose an option--</option>
    <option value="dog">Dog</option>
    <option value="cat">Cat</option>
    <option value="hamster">Hamster</option>
    <option value="parrot">Parrot</option>
    <option value="spider">Spider</option>
    <option value="goldfish">Goldfish</option>
</select>
</template>

<style>
@media (min-width: 1024px) {
  .todo {
    min-height: 100vh;
    align-items: center;
  }
}
span {
  color:red;
}

</style>

