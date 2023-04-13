<template>

  <div class="container">

    <ToolBox class="toolbox" @selectColor="updateSelectedColor" @pixelSize="updatePixelSize"/>

    <div class="pixel-editor">
      <draw-board :selected-color="selectedColor" :pixel-size="pixelSize" />
    </div>

  </div>
  
</template>

<script>
// import ColorPalette from "./CorPalette.vue";
import ToolBox from "./ToolBox.vue";
import DrawBoard from "./DrawBoard.vue";

export default {
  components: {
    // ColorPalette,
    ToolBox,
    DrawBoard,
  },
  data() {
    return {
      selectedColor: "#000000",
      pixelSize: 10
    };
  },
  methods: {
    updateSelectedColor(color) {
      this.selectedColor = color;
    },
    updatePixelSize(size){
      this.pixelSize = size;
    }
  },
};
</script>

<style>


.container{
  position: relative;
}

.pixel-editor {
  display: flex;
  justify-content: center;
  align-items: center;
  /*height: 90vh;*/

}
</style>
