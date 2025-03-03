<template>
  <main>
    <BtnComponent
      v-for="(item, index) in database"
      :key="index"
      :btnText="item.btnText"
      :src="item.src"
      :alt="item.alt"
    />
  </main>
</template>


<script setup>
import BtnComponent from './components/btnComponent.vue';
import { ref } from 'vue';

let database = ref([
  {
    btnText: "+1",
    src: "./src/assets/mario.svg",
    alt: "Mario popup for adding one to the count",
  },
  {
    btnText: "-1",
    src: "./src/assets/goomba.svg",
    alt: "Goomba popup for subtracting one from the count",
  },
])

</script>