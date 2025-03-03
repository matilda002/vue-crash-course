<template>
    <div id="container">
        <button class="popup" @click="togglePopup">
            {{ btnText }}
            <div class="popup-content" ref="popupContent">
                <img :src="src" :alt="alt" />
            </div>
        </button>
    </div>
</template>

<script>
export default {
    name: 'BtnComponent',
    props: {
        src: String,
        alt: String,
        btnText: String
    },
    methods: {
        togglePopup() {
            const popup = this.$refs.popupContent;
            if (popup) {
                popup.classList.toggle('show');
            }
        }
    }
};
</script>

<style scoped>
@import "../scss/main.scss";

#container {
    border-width: 0.3rem;
}
</style>