<template>
    <p>Dnes si vypil {{ actual }} L vody.</p>
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
        },

        data() {
            return {
                drinkingRecords: [],
                dailyGoal: 0,
                actual: 0,
            }
        }
        
    }
</script>

<style lang="scss" scoped>

</style>