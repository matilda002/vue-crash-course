<template>
        <button class="popup" @click="handleCount">
            {{ btnText }}
            <div class="popup-content" ref="popupContent">
                <img :src="src" :alt="alt" />
            </div>
        </button>
</template>

<script>
export default {
    name: "BtnComponent",
    props: {
        src: String,
        alt: String,
        btnText: String,
        action: String,
    },
    methods: {
        handleCount() {
            this.$emit("update-count", this.action);
            this.togglePopup();
        },
        togglePopup() {
            const popup = this.$refs.popupContent;
            if (popup) {
                popup.classList.toggle("show");
            }
        },
    },
};
</script>
