<script setup lang="ts">
import { ref } from "vue";

const mmol = ref("");
const mgdl = ref("");

const handleMmolEvent = () => {
  mgdl.value = (18.0182 * Number(mmol.value)).toFixed(3);
}

const handlemgDlEvent = () => {
  mmol.value = (Number(mgdl.value) / 18.0182).toFixed(3);
}

const onlyNumber = ($event) => {
   //console.log($event.keyCode); //keyCodes value
   let keyCode = ($event.keyCode ? $event.keyCode : $event.which);
   if ((keyCode < 48 || keyCode > 57) && keyCode !== 46) { // 46 is dot
      $event.preventDefault();
   }
}

</script>

<template>
  <div>
    <h1>Blood Sugar converter</h1>
    <div class="converter-container">
      <div class="converter-input-container">
        <label htmlFor="mmol">Blood sugar level in mmol/l</label>
        <input class="input-element" id="mmol" v-model="mmol" @input="handleMmolEvent()" @keypress="onlyNumber"/>
      </div>

      =

      <div class="converter-input-container">
        <label htmlFor="mgdl">Blood sugar level in mg/dl</label>
        <input class="input-element" id="mgdl" v-model="mgdl" @input="handlemgDlEvent()" @keypress="onlyNumber"/>
      </div>
    </div>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}

.converter-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.converter-input-container {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.input-element {
  height: 30px;
  font-size: 20px;
  text-align: center;
}
</style>
