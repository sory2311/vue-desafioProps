<template>
<div>
<ul class="la"> 
  <li v-for="(tarea,index) in tareas" :key="index">{{tarea}}<button @click="eliminar(index)">Eliminar</button> </li>
</ul>
</div>
</template>

<script>
export default {
name: "compHijo",
props: {
dato: String,
tareas: Array
},
methods:{
  eliminar(index){
    this.$emit("eliminarTarea", index);
  }
}
};
</script>


<style scoped>
.la{ 
  color: black;

}

</style>