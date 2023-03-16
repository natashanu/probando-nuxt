<template>
    <div>
      <input type="text" v-model="newToDo">
      <button v-on:click="addToDo">Agregar tarea</button>
      <ul>
        <div class="lista" v-for="tarea in tareas" :key="tarea.id">
          <li>
            <label :for="tarea.id">{{ tarea.descripcion }}</label>
            <input type="checkbox" :id="tarea.id" :value="tarea.id" v-model="checkedToDo">
          </li>
        </div>
      </ul>
      <p>Tengo {{ count }} tareas que realizar</p>
      <button v-if="checkedToDo && checkedToDo.length>0" v-on:click="removeToDo">Eliminar tareas</button>
    </div>

</template>

<script>
let idElemento = 0;

export default {
  name: 'Tareas',
  components:{

  },
  data(){
    return{
      newToDo:"",
      tareas: [

      ],
      count : 0, 
      checkedToDo: []
    }
  },
  methods:{
    addToDo: function(){
      if(this.newToDo){
        this.tareas.push({
          id: idElemento,
          descripcion: this.newToDo.trim()
        })
        this.newToDo = "";
        this.count ++
        idElemento++
      }
      
    },
    removeToDo: function(){
      this.checkedToDo.forEach(element => {
        this.tareas = this.tareas.filter(function(item) {
          return item.id !== element
        })  
        this.count = this.tareas.length
        
      });
    }
  }
}
</script>

<style scoped>
  ul{
    list-style: none;
  }
</style>