<template>
  <main>
    <div id="container">
      <h1>Add and subtract to the count</h1>

      <div id="countContainer">
        <button class="popup" @click="
          togglePopup();
        add();
        ">
          +1
          <div class="popup-content" ref="popup">
            <img src="./assets/mario.svg" alt="Mario popup for adding one to the count" aria-hidden="true" />
          </div>
        </button>
        <span id="numValue">{{ number }}</span>
        <button class="popup" @click="
          togglePopup2();
        sub();
        ">
          -1
          <div class="popup-content" ref="popup2">
            <img src="./assets/goomba.svg" alt="Goomba popup for subtracting one from the count" aria-hidden="true" />
          </div>
        </button>
      </div>
    </div>
  </main>
</template>

<script>
import { onMounted, ref } from "vue";

export default {
  setup() {
    const popup = ref(null);
    const popup2 = ref(null);
    const number = ref(0);

    // Toggle the visibility of the popup
    function togglePopup() {
      if (popup.value) {
        popup.value.classList.toggle("show");
      }
    }

    function togglePopup2() {
      if (popup2.value) {
        popup2.value.classList.toggle("show");
      }
    }

    onMounted(() => {
      const savedNumber = localStorage.getItem("number");
      if (savedNumber !== null) {
        number.value = parseInt(savedNumber, 10);
      }
    });

    const updateLocalStorage = () => {
      localStorage.setItem("number", number.value);
    };

    function add() {
      number.value++;
      updateLocalStorage();
    }

    function sub() {
      number.value--;
      updateLocalStorage();
    }

    return { popup, popup2, number, togglePopup, togglePopup2, add, sub };
  },
};
</script>

<style scoped>
@import "./scss/main.scss";
</style>
