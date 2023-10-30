<script setup>
  import { ref } from 'vue';
  const number_1 = ref(null);
  const number_2 = ref(null);
  const result = ref(null);

  function plus(){
    result.value = number_1.value + number_2.value;
  }

  function minus(){
    result.value = number_1.value - number_2.value;
  }

  function multiply(){
    result.value = number_1.value * number_2.value;
  }

  function divide(){
    if(number_2.value)
      result.value = number_1.value / number_2.value;
    else
      result.value = "undefined"
  }
</script>

<template>
  <div>
    <label>Number 1</label><br />
    <input class="border border-black" id="number1" type="number" placeholder="Number 1" v-model="number_1" />
  </div>
  <div>
    <label>Number 2</label><br />
    <input class="border border-black" id="number2" type="number" placeholder="Number 2" v-model="number_2"/>
  </div>

  <div>
    <button class="bg-gray-300 px-3 py-2" @click="plus">+</button>
    <button class="bg-gray-300 px-3 py-2" @click="minus">-</button>
    <button class="bg-gray-300 px-3 py-2" @click="multiply">*</button>
    <button class="bg-gray-300 px-3 py-2" @click="divide">/</button>
  </div>
  
  <p id="result">Result : {{ result }}</p>
</template>