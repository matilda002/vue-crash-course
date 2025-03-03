<template>
  <main>
    <div id="container">
      <h1>Add and subtract to the count</h1>
      <div id="countContainer">
        <p>Current count: {{ count }}</p>
        <BtnComponent v-for="(item, index) in database" :key="index" :btnText="item.btnText" :src="item.src"
          :alt="item.alt" :action="item.action" @update-count="updateCount" />
      </div>
    </div>

  </main>
</template>

<script setup>
import BtnComponent from "./components/Btn.vue";
import { ref } from "vue";

let database = ref([
  {
    btnText: "+1",
    src: "./src/assets/mario.svg",
    alt: "Mario popup for adding one to the count",
    action: "add",
  },
  {
    btnText: "-1",
    src: "./src/assets/goomba.svg",
    alt: "Goomba popup for subtracting one from the count",
    action: "sub",
  },
]);

let count = ref(0);

function updateCount(action) {
  if (action === "add") {
    count.value++;
  } else if (action == "sub") {
    count.value--;
  }
}
</script>
