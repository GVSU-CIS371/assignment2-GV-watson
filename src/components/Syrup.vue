<template>
  <div class="syrup" :style="{ backgroundColor: isSyruped.color }"></div>
</template>

<script setup lang="ts">
import type { SyrupType } from "./stores/beverage";

const props = defineProps<{ isSyruped: SyrupType }>();


 
    //name: "Black Tea",
    //color: "#8B4513",
 
    //id: "b2",
   // name: "Green Tea",
    //color: "#C8E6C9",
  
    //id: "b3",
    //name: "Coffee",
   // color: "#6F4E37",




</script>
<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  //background-color: #c6c6c6;
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
