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
    <input id="number1" type="number" placeholder="Number 1" v-model="number_1" />
  </div>
  <div>
    <label>Number 2</label><br />
    <input id="number2" type="number" placeholder="Number 2" v-model="number_2"/>
  </div>

  <div>
    <button @click="plus">+</button>
    <button @click="minus">-</button>
    <button @click="multiply">*</button>
    <button @click="divide">/</button>
  </div>
  
  <p id="result">Result : {{ result }}</p>
</template>