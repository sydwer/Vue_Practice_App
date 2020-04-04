<template>
<div v-on:click="test += 1"> 

    <p> {{button.type}}</p>
    <h2>{{test}}</h2>
</div>
</template>

<script>
export default {
    props: {
        button: Object,
    },
    data() {
        return {

            test: 0
        }
    }
}
</script>

<style scoped>

</style>