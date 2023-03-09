<template>
  <div class="palette">
    <div v-for="color in colors" :style="{ backgroundColor: color }" @click="selectColor(color)"></div>
  </div>
</template>

<script>
export default {
  props: {
    colors: {
      type: Array,
      default: () => ["#ffffff", "#000000", "#ff0000", "#00ff00", "#0000ff"],
    },
    selectedColor: {
      type: String,
      default: "#000000",
    },
  },
  methods: {
    selectColor(color) {
      this.$emit("selectColor", color);
    },
  },
};
</script>

<style>
.palette {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.palette div {
  width: 30px;
  height: 30px;
  margin: 5px;
  cursor: pointer;
}
</style>
