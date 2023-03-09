<template>
  <div class="pixel-editor">
    <color-palette :colors="colors" :selected-color="selectedColor" @selectColor="updateSelectedColor" />
    <draw-board :selected-color="selectedColor" />
  </div>
</template>

<script>
import ColorPalette from "./CorPalette.vue";
import DrawBoard from "./DrawBoard.vue";

export default {
  components: {
    ColorPalette,
    DrawBoard,
  },
  data() {
    return {
      colors: ["#ffffff", "#000000", "#ff0000", "#00ff00", "#0000ff"],
      selectedColor: "#000000",
    };
  },
  methods: {
    updateSelectedColor(color) {
      this.selectedColor = color;
    },
  },
};
</script>

<style>
.pixel-editor {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>
