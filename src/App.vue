<template>
<div id="app">
<div>
  <h1>Agrega tareas a tu lista</h1>
  <label class="la">Tarea</label>
<input type="text" v-model="tarea"/>
<button @click="add">Agregar Tarea</button>
</div>
<compHijo :tareas="tareas" @eliminarTarea="eliminar"></compHijo>
</div>
</template>

<script>
import compHijo from "./components/compHijo.vue";

export default {
name: 'app',
  components: {
    compHijo
    },
  data() {
return {
  tarea:" ",
tareas: [],

};
},
methods: {
add() {
  if(this.tarea !== "") { 
this.tareas.push(this.tarea),
this.tarea ="";
}else{
  alert("Atención: Se debe ingresar una tarea")
}
},
eliminar(index){
  this.tareas.splice(index,1);
}
}
};

</script>

<style>
#app {
  font-family: 'Calibri', sans-serif;
  color: rgb(11, 153, 23);
  margin: 15px;
  
 
}
.la{ 
  color: black;
  font-weight: bold;
  font-size: 20px;
  margin-right: 5px;
}
</style>