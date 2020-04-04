<template>
  <div id="app">
    <div class="starter-info" v-if= "counter === 0">
      <h1>Howdy</h1>
      <button @click="counter += 1">start</button>
    </div>
    <h2>{{counter}}</h2>
   
    <button v-for="button in buttons" :key="button.id">
      <RandomButton />
    </button>

  </div>
</template>

<script>
import RandomButton from "@/components/RandomButton"
export default {
  components: {
    RandomButton,
  },
  data(){
    return{
      counter: 0,
      buttons: [{
       
      }]
    }
  }
}
// function addCounter(){
//   return this.counter += 1
// }
// function addButton(){
//   addCounter();
//   buttons.push({type: "test", id: counter})
// }

</script>

<style lang="scss">

</style>
