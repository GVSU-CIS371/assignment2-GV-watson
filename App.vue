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
          <input type="radio" id="b1"  :value="`Black Tea`" v-model="BaseBeverageType" />
          <label for="b1">No Cream</label>

          <input type="radio" id="b2"  :value="`Green Tea`"  v-model="BaseBeverageType" />
          <label for="b2">Milk</label>

          <input type="radio" id="b3"  :value="`Coffee`"  v-model="BaseBeverageType" />
          <label for="b3">Cream</label>
        </div>

        <div>
          <input type="radio" id="c1"  :value="`No Cream`" v-model="CreamerType" />
          <label for="c1">No Cream</label>

          <input type="radio" id="c2"  :value="`Milk`"  v-model="CreamerType" />
          <label for="c2">Milk</label>

          <input type="radio" id="c3"  :value="`Cream`"  v-model="CreamerType" />
          <label for="c3">Cream</label>

          <input type="radio" id="c4"  :value="`Half & Half`" v-model="CreamerType" />
          <label for="c4">Half & Half</label>
        </div>
        
        <div>
          <input type="radio" id="s1"  :value="`No Syrup`" v-model="SyrupType" />
          <label for="s1">No Syrup</label>

          <input type="radio" id="s2"  :value="`Vanilla`"  v-model="SyrupType" />
          <label for="s2">Vanilla</label>

          <input type="radio" id="s3"  :value="`Caramel`"  v-model="SyrupType" />
          <label for="s3">Caramel</label>

          <input type="radio" id="s4"  :value="`Hazelnut`" v-model="SyrupType" />
          <label for="s4">Hazelnut</label>
        </div>

      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";

import { BaseBeverageType, CreamerType, SyrupType } from "./stores/beverage";
import { bases, creamers, syrups } from "./stores/beverage";

const BaseBeverageType = ref(0);
const CreamerType = ref(0);
const SyrupType = ref(0);


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