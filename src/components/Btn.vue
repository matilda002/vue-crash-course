<template>
    <button class="popup" @click="handleCount">
        {{ btnText }}
        <div class="popup-content" :class="{ show: isPopupVisible }">
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
    data() {
        return {
            isPopupVisible: false,
        };
    },
    methods: {
        handleCount() {
            this.$emit("update-count", this.action);
            this.showPopup();
        },
        showPopup() {
            this.isPopupVisible = true;
            setTimeout(() => {
                this.isPopupVisible = false;
            }, 2000);
        },
    },
};
</script>