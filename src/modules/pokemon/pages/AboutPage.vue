<template>
  <h1>About page</h1>
  <hr>
  <h2>{{name}}</h2>
  <button @click="onChangeName">
    Cambiar nombre
  </button>
</template>

<script>
export default {

data(){
  return {
    name:'Enrique'
  }
},
methods:{
  onChangeName(){
    this.name='Melissa'
  }
}

}
</script>

<style>

</style>