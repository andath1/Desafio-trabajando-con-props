<template>
  <br>
  <form class="form">
    <label for="todoitem">Tarea</label>
    <input type="text" v-model="input" id="todoitem" placeholder="Ingresar una nueva tarea"/>
    <button type="button" class="btn" v-on:click.prevent="add()"><span>Añade</span> </button>
  </form>
  <ItemsCopia :tareas="this.tareas" @deleteItem="deleteElement"/>
</template>
<script>
import ItemsCopia from "./components/ItemsCopia.vue";
export default {
  name: 'App',
  components: {
    ItemsCopia,
  },
  data(){
    return {
      tareas: [],
      input: ""
    }
  },
  methods: {
    add(){
      this.tareas.push(this.input);
      this.input = "";
    },
    deleteElement(index){
      this.tareas.splice(index, 1);
    }
  }
}
</script>

<style>
label{
  font-size: 30px;
  margin-right: 20px;
  margin-left: 20px;
  
}

.form{
  margin-left: 400px;
  margin-bottom: 50px;
}
li{
  margin-left: 450px;
  margin-bottom: 10px;
  font-size: 20px;

}
.btn {
    background-color: white;
    border-radius: 10px;
    margin-left: 10px;
    border: 4px solid #4e87f1;
}
</style>
