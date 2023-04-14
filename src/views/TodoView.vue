<script setup>
  let msg = "À faire : ";
</script>

<template>
  <div class="title">
    <h1>Voici la todo list </h1>
    <span>{{ msg }}</span>
  </div>
  <div class="durée">
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
    <label for="name">Nom de la tâche : </label>
    <input type="text" id="name" name="name" required minlength="4" maxlength="12" size="10">
  </div>
  <div class="apply">
    <button class="favorite styled" type="button">
      Ajouter la tâche
    </button>
  </div>
</template>

<style>
span {
  color:red;
}
</style>

