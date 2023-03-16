<template>
  <div class="principal">
    <h1>¡Hola!</h1>
    <h2>Aquí están mis tareas por hacer</h2>
    <Tareas/>
  </div>
</template>

<script>
import Tareas from "~/components/Tareas";


export default {
  name: 'IndexPage',
  components:{
    Tareas
  }, 
}
</script>

<style>
  .principal{
    text-align: center;
    width: fit-content;
    margin: auto;
  }
</style>
