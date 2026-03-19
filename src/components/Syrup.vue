<template>
  <div
    v-if="props.type !== 'No Syrup'"
    class="syrup"
    :style="{ backgroundColor: getColor() }"
  ></div>
</template>

<script setup lang="ts">
type Props = {
  type: string;
};

const props = defineProps<Props>();

const getColor = () => {
  switch (props.type) {
    case "Vanilla":
      return "#f3e5ab";
    case "Caramel":
      return "#c68e17";
    case "Hazelnut":
      return "#8b5a2b";
    default:
      return "transparent";
  }
};
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
