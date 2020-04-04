<template>
  <div id="app">
    <div class="starter-info" v-if= "counter === 0">
      <h1>Howdy</h1>
      <button v-on:click="counter += 1"> Start </button>
    </div>
    <h2>{{counter}}</h2>
  <div v-if="counter > 0" class="new-buttons"> 
    <div v-on:click="addButton" v-for="button in buttons" :key="button.id" class="random-buttons">
      <RandomButton :button="button"/>
    </div>
    <!-- <button v-on:click="addButton" v-for="button in colorButtons" :key="button.id">
      <ColorButton :button="button"/>
    </button> -->
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
      buttonTypes: ["color", "sound", "size",], 
      buttons: [{
        type: "color",
        id: this.counter 
      }],
    }
  },
  computed: {
    colorButtons: function(){
      return this.buttons.filter(button => button.type === "color")
    }
  },
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
  div{
    background: beige;
  }
  .starter-info button {
    height: 25px;
  }
  .new-buttons{
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    grid-gap: 4px;
  }
</style>
