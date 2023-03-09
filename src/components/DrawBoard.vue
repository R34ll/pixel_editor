<template>
  <div class="draw-board" @mousedown="startDrawing" @mousemove="drawPixel" @mouseup="stopDrawing"></div>
</template>

<script>
export default {
  props: {
    selectedColor: {
      type: String,
      default: "#ffffff",
    },
  },
  data() {
    return {
      drawing: false,
    };
  },
  methods: {
    startDrawing() {
      this.drawing = true;
    },
    stopDrawing() {
      this.drawing = false;
    },
    drawPixel(event) {
      if (!this.drawing) return;
      const board = event.target;
      const rect = board.getBoundingClientRect();
      const x = event.clientX - rect.left;
      const y = event.clientY - rect.top;
      const color = event.buttons === 1 ? this.selectedColor : "#ffffff";
      const pixel = document.createElement("div");
      pixel.style.backgroundColor = color;
      pixel.style.width = "5px";
      pixel.style.height = "5px";
      pixel.style.position = "absolute";
      pixel.style.left = x + "px";
      pixel.style.top = y + "px";
      board.appendChild(pixel);
    },
  },
};
</script>

<style>
.draw-board {
  width: 400px;
  height: 400px;
  position: relative;
  border: 1px solid #000000;
}
</style>
