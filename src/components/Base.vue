<template>
  <div class="baseBeverage" :style="{ backgroundColor: baseColor }"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";

const props = defineProps({
  name: {
    type: String,
    default: "Black Tea",
  },
});

const baseColor = computed(() => {
  switch (props.name) {
    case "Coffee":
      return "#6F4E37";
    case "Green Tea":
      return "#C8E6C9";
    case "Black Tea":
      return "#8B4513";
    default:
      return "#8B4513";
  }
});
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>
