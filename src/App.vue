<template>
  <div id="app">
    <div class="starter-info" v-if= "counter === 0">
      <h1>Howdy</h1>
      <button v-on:click="counter += 1">start</button>
    </div>
    <h2>{{counter}}</h2>
  <div v-if="counter > 0" class="new-buttons"> 
    <button v-on:click="addButton" v-for="button in buttons" :key="button.id">
      <RandomButton />
    </button>
  </div>

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
  },
  methods: {
    addButton: function() {
      this.counter += 1
      this.buttons.push({type: "test", id: this.counter})
    },
  }
}


</script>

<style lang="scss">

</style>
