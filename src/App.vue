<template>
  <div id="app">
    <div class="starter-info" v-if= "counter === 0">
      <h1>Howdy</h1>
      <button v-on:click="counter += 1"> Start </button>
    </div>
    <h2>{{counter}}</h2>
  <div v-if="counter > 0" class="new-buttons"> 
    <button v-on:click="addButton" v-for="button in buttons" :key="button.id">
      <RandomButton :button="button"/>
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
      buttonTypes: ["color", "sound", "size"], 
      buttons: [{
        type: "color",
        id: this.counter 
      }]
    }
  },
  // computed: {
  //   randomType: function (){
  //     const types = ["color", "sound", "size"];
  //     const randomType = types[Math.floor(Math.random() * types.length)];
  //     return randomType
  //   }
  // },
  methods: {
    addCounter: function (){
      this.counter += 1
    },
    randomType: function (){
      let randomButtonType = this.buttonTypes[Math.floor(Math.random() * this.buttonTypes.length)];
      return randomButtonType
    },
    addButton: function() {
      this.addCounter()
      this.buttons.push({type: this.randomType(), id: this.counter})
    },
  }
}


</script>

<style lang="scss">
  .starter-info button {
    height: 25px;
  }
</style>
