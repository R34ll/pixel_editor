<template>
  <div class="palette">
    <!-- <div v-for="color in colors" :style="{ backgroundColor: color }" @click="selectColor(color)"></div> -->
    <input type="color" shape="poly" name="color" ref="colorDiv" @change="event => selectColor(event)">
</div>
</template>

<script>
export default {
  props: {
    selectedColor: {
      default: "#000000",
    },
  },

  methods: {
    selectColor(event) {
      let color = event.target.value
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
