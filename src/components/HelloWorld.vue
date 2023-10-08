<script setup lang="ts">
import { ref } from "vue";

defineProps<{ msg: string }>();

const count = ref(0);
</script>

<template>
  <div>
    <h1>Blood Sugar converter</h1>
    <div class="converter-container">
      <div class="converter-input-container">
        <label htmlFor="mmol">Blood sugar level in mmol/l</label>
        <input class="input-element" id="mmol" />
      </div>

      =

      <div class="converter-input-container">
        <label htmlFor="mgdl">Blood sugar level in mg/dl</label>
        <input class="input-element" id="mgdl" />
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
