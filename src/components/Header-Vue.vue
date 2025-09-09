<template>
    <transition name="slide-right">
        <div class="warning" v-if="isVisible">
            <button class="close" @click="hideElement">X</button>
            <p>Táto aplikácia slúži ako prezentácia mojich znalostí so zameraním na <strong>Vue.js</strong>.</p>
            <p>Stále na nej pracujem, preto môže obsahovať chyby a nemusí fungovať správne.</p>
        </div>
    </transition>
    
    <header>
        <h1>Water reminder by Kilečko 🥤</h1>
    </header>
</template>

<script>
    export default {
        data() {
            return {
                isVisible: true
            }
        },
        methods: {
            hideElement() {
                this.isVisible = false
            }
        },
    }
</script>

<style scoped>
    .slide-right-enter-active,
    .slide-right-leave-active {
        transition: all 0.4s ease;
    }

    .slide-right-enter-from,
    .slide-right-leave-to {
        opacity: 0;
        transform: translateX(100%);
    }
</style>