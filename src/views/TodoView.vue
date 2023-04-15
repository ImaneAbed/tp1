<script>
export default {
    data() {
        return {
            tasks: [{
                    time: 2,
                    responsable: "Alice",
                    todo: "promener le chien"
                }
            ]
        }
    },
    methods: {
      // Add Task
      SubmitTask(time, responsable, todo) {
        if(time.length===0 || responsable.length===0 || todo.length===0){
          return;
        }
        let nb_task=0;
        let total_time=0
        for(let i = 0; i < this.tasks.length; i++){
          if(this.tasks[i].responsable==responsable){
            nb_task=nb_task+1;
            total_time=total_time+this.tasks[i].time;
          }
        }
        if(nb_task>2 || total_time+time>10){
          return;
        }
        this.tasks.push({
          time: time,
          responsable: responsable,
          todo: todo
        })        
      },
      // delete task
      deleteTask(index) {
            this.tasks.splice(index, 1)
      },
      // edit task
      EditTask(index) {
        this.task = this.tasks[index].time,
        this.task = this.tasks[index].responsable,
        this.task = this.tasks[index].todo,
        this.editTask = index
      }
    }
}
</script>

<template>
  <div class="title">
    <h1>Voici la todo list </h1>
  </div>
  <div class="add">
      <label for="time">Durée de la tâche (0-10 heures) : </label>
      <input type="number" id="time" name="time" min="0" max="10" v-model="timeValue">
      <label for="responsable-select">Choix du responsable : </label>
      <select name="respopnsable" id="responsable-select" v-model="responsableValue">
        <option value="">--Responsable--</option>
        <option value="Alice">Alice</option>
        <option value="Bob">Bob</option>
        <option value="Oscar">Oscar</option>
      </select>
      <label for="name">Nom de la tâche (4 à 12 caractères): </label>
      <input type="text" id="name" name="name" required minlength="4" maxlength="12" size="10" placeholder="Tâche..."  v-model="nameValue">
      <button class="add-button" @click="SubmitTask(timeValue,responsableValue,nameValue)">
        Ajouter la tâche
      </button>
  </div>
  <div class = "table">
    <table border>
      <thead>
        <tr>
          <th>Durée</th>
          <th>Responsable</th>
          <th>Tâche</th>
          <th>Faite !</th>
          <th>Modifier</th>
          <th>Supprimer</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(task,index) in tasks" :key="index">
                <td>{{task.time}}</td>
                <td>{{task.responsable}}</td>
                <td>{{task.todo}}</td>
          <td>boutton Fait !</td>
          <td>
            <button class="edit" @click="EditTask(index)">Modifier</button>
          </td>
          <td>
            <button class="delete" @click="deleteTask(index)">Supprimer</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


