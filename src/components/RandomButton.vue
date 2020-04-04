<template>
    <button v-if="button.type === 'size'" v-bind:style="{height:this.randomDimension(), width:this.randomDimension()}" class = "non-color-button"></button>

    <button v-else-if="button.type === 'color'" v-bind:style="{backgroundColor:this.randomColor()}" class = "non-size-button">
    </button>
    <button v-else-if="button.type === 'sound'" class= "non-size-button non-color-button" > Sounds</button>






</template>

<script>
// import ColorButton from "@/components/ColorButton"
export default {
    props: {
        button: Object,
    },
    data() {
        return {
            // type: button.type,
            test: 0,
            colors: [
                "#2e564d",
                "#085490",
                "#8d9652",
                "pink",
                "#39c58c",
                "#22e8c9",
                "#e0756b",
                "#009a6e",
                "#d009ea",
                "#8119f4",
                "#53f3e3",
                "#5761f5",
            ]
        }
    },
    methods: {
        randomColor: function (){
            return this.colors[Math.floor(Math.random() * this.colors.length)]
        },
        randomDimension: function(){
            let randomNumber = Math.floor(Math.random() * 8) + 1;
            return `${randomNumber}rem`
        }
    }
}
</script>

<style scoped>
    button{
        border-radius: 50%;
    }
    .non-size-button{
        height: 3rem;
        width: 5rem;
    }
    .non-color-button{
        background-color: #607d8bd4;
    }
</style>