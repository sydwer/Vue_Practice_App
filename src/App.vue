<template>
  <div id="app">
    <h1 v-if= "buttons.length === 1">Howdy</h1>
    <ul> 
      <li v-for="button in buttons" :key="button.id"> {{button.type}}</li>
    </ul>

  </div>
</template>

<script>
export default {
  data(){
    return{
      buttons: [{
        type: "start",
        id: 1,
      }]
    }
  }
}

</script>

<style lang="scss">

</style>
