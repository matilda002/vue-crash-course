<template>
  <main>
    <div id="container">
      <h1>Add and subtract the total</h1>

      <div id="countContainer">
        <button class="btn" @click="add">+1</button>
        <span id="numValue">{{ number }}</span>
        <button class="btn" @click="sub">-1</button>
      </div>
    </div>
  </main>
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