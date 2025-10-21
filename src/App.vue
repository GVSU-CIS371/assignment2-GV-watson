<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>

        
        <div>
          <template v-for="base in bases" :key="base.id">
            <input
              type="radio"
              name="base"
              :id="base.id"
              :value="base"
              v-model="user_Base"
            />
            <label :for="base.id">{{ base.name }}</label>
          </template>
        </div>

        
        <div>
          <template v-for="cream in creamers" :key="cream.id">
            <input
              type="radio"
              name="creamer"
              :id="cream.id"
              :value="cream"
              v-model="user_Creamer"

            />
            <label :for="cream.id">{{ cream.name }}</label>
          </template>
        </div>

        
        <div>
          <template v-for="syrup in syrups" :key="syrup.id">
            <input
              type="radio"
              name="syrup"
              :id="syrup.id"
              :value="syrup"
              v-model="user_Syrup"
            />
            <label :for="syrup.id">{{ syrup.name }}</label>
          </template>
        </div>

      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";

import { bases, creamers, syrups } from "./stores/beverage";


const user_Base = ref(bases.value[0]);
const user_Creamer = ref(creamers.value[0]);
const user_Syrup = ref(syrups.value[0]);


</script>


<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>