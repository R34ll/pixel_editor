

<template>
    <div class="board">
        <img class="tool" src="../assets/pencil.png" width="40" height="40" >
        <img class="tool" src="../assets/eraser.png" @click="eraser" width="40" height="40" >


        <ColorPalette class="tool" @selectColor="updateSelectedColor" />



        <div class="pixel-size">
            <p>Pixel size:</p>
            <input type="range" value="10" class="pixel-range" @change="event => updatePixelSize(event)">
        </div>

    </div>

</template>

<script>

import ColorPalette from "./CorPalette.vue";

  export default {
    components:{
        ColorPalette
    },

    methods: {
        updateSelectedColor(color) {
            this.$emit("selectColor", color);
        },

        updatePixelSize(event){
            this.$emit("pixelSize",event.target.value);
        },  

        eraser(){
            this.$emit("selectColor","#ffffff")
        }
    },
  };
</script>



<style>

.pixel-size{
    display: flex;
    align-items: center;
    margin-left: 50%;
    color: black; 
}

.pixel-size input[type="range"] {
  -webkit-appearance: none;
  background-color: black; 
  height: 2px;
  margin: 0;
  width: 100%;
}

.pixel-size input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  background-color: black; 
  height: 15px;
  width: 15px;
  border-radius: 50%;
}

.tool{
    cursor: pointer;
    padding: 15px;
}

.board{
    display: flex;
    align-items: center;
    border-radius: 10px;

    background-color: gray;
    height: 100px;
}
</style>