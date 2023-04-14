<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      // update component state
      this.count++
    }
  }
}
</script>

<template>
  <div class="title">
    <h1>Voici la todo list </h1>
  </div>
  <div class = "table">
    <table border>
      <thead>
        <tr>
          <th>Tâche</th>
          <th>Responsable</th>
          <th>Durée</th>
          <th>Faite !</th>
          <th>Modifier</th>
          <th>Supprimer</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>The table body</td>
          <td>with two columns</td>
          <td>The table body</td>
          <td>The table body</td>
          <td>The table body</td>
          <td>The table body</td>
        </tr>
      </tbody>
    </table>
  </div>
  <div class="time">
    <label for="tentacles">Durée de la tâche (0-10 heures) : </label>
    <input type="number" id="tentacles" name="tentacles" min="0" max="10">
  </div>
  <div class="responsable">
    <label for="responsable-select">Choix du responsable : </label>
    <select name="respopnsable" id="responsable-select">
      <option value="">--Responsable--</option>
      <option value="alice">Alice</option>
      <option value="bob">Bob</option>
      <option value="oscar">Oscar</option>
    </select>
  </div>
  <div class="todo">
    <label for="name">Nom de la tâche (4 à 12 caractères): </label>
    <input type="text" id="name" name="name" required minlength="4" maxlength="12" size="10">
  </div>
  <div class="button">
    <button class="add-button" type="button">
      Ajouter la tâche
    </button>
  </div>
  <div>
    <button @click="increment">ce boutton a ete appyé {{ count }} fois</button>
  </div>
</template>

<style>
span {
  color:red;
}
</style>

