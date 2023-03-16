<template>
  <div>
    <button>Un botton</button>
    <Tareas/>
  </div>
</template>

<script>
import Tareas from "~/components/Tareas.vue";

export default {
  name: 'IndexPage',
  components:{
    Tareas
  }
}
</script>
