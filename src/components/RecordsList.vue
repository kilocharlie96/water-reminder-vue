<template>
    <new-record-form></new-record-form>
    <ul>
        <li v-for="(waterRecord, index) in drinkingRecords" :key="index">
            <drinking-record :waterAmount="waterRecord.litres" :litresTotalNow="waterRecord.litresTotalNow" :litresTotalDay="waterRecord.litresTotalBefore" :time="waterRecord.atTime" :remainingToTarget="waterRecord.remainingToTarget"/>
        </li>
    </ul>
</template>

<script>
    import NewRecordForm from './NewRecordForm.vue';
    import DrinkingRecord from './DrinkingRecord.vue';

    export default {
        components: {
            NewRecordForm,
            DrinkingRecord
        }
        
    }
</script>

<style lang="scss" scoped>

</style>