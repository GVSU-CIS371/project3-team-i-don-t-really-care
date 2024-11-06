<template>
<div class="syrup" :style="{ backgroundColor: syrupColor }"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";

const props = defineProps({
  name: {
    type: String,
    default: "Vanilla",
  },
});

const syrupColor = computed(() => {
  switch (props.name) {
    case "Vanilla":
      return "#FFEFD5";
    case "Caramel":
      return "#DAA520";
    case "Hazelnut":
      return "#6B4423";
  }
});
</script>


<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>