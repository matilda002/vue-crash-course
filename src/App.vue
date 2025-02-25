<template>
  <h1>Add and subtract the total</h1>

  <button @click="add">+1</button>
  {{ number }}
  <button @click="sub">-1</button>
</template>

<script>
import { onMounted, ref } from 'vue';

export default {
  setup() {
    const number = ref(0);

    onMounted(() => {
      const savedNumber = localStorage.getItem('number');
      if (savedNumber !== null) {
        number.value = parseInt(savedNumber, 10);
      }
    });

    const updateLocalStorage = () => {
      localStorage.setItem('number', number.value);
    };

    function add() {
      number.value++;
      updateLocalStorage();
    }
    function sub() {
      number.value--;
      updateLocalStorage();
    }
    return { number, add, sub };
  },
};

</script>