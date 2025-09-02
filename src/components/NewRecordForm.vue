<template>
    <h3>Pridaj nový záznam</h3>
    <form @submit.prevent="addRecord">
        <input type="number" step="0.1" v-model="newRecord" autofocus> litrov
    </form>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>

</style>