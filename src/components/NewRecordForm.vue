<template>
    <h3>Pridaj nový záznam</h3>
    <form @submit.prevent="submitRecord">
        <input type="number" step="0.1" v-model="waterAmount" autofocus> litrov
    </form>
    <p>{{ waterAmount }}</p>
</template>

<script>
    export default {
        data() {
            return {
                waterAmount: 0.0,
            }
        },
        methods: {
            submitRecord() {
                this.$emit('new-record-submitted', this.waterAmount)
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>