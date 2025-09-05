<template>
    <p>Dnes si vypil {{ waterDrunkTotal }} L vody.</p>
    <p>Tvoj cieľ je {{ presetGoal }} L vody.</p>
    <new-record-form @new-record-submitted="pushRecord( $event )"></new-record-form>
    <ul>
        <li v-for="(waterRecord, index) in waterRecords" :key="index">
            <p>{{ waterRecord.waterDrunkNow }}</p>
            <p>{{ waterRecord.waterDrunkTotal }}</p>
        </li>
    </ul>
</template>

<script>
    import NewRecordForm from './NewRecordForm.vue';
    import DrinkingRecord from './DrinkingRecord.vue';

    export default {
        props: ['presetGoal'],

        components: {
            NewRecordForm,
            DrinkingRecord
        },

        data() {
            return {
                dailyGoal: 0.0,
                waterDrunkTotal: 0.0,
                waterRecords: [],
            }
        },
        methods: {
            pushRecord(data) {
                console.log(data)
                this.dailyGoal = data
                console.log(data)
                this.waterDrunkTotal += data
                this.waterRecords.push({
                    "waterDrunkNow": data,
                    "waterDrunkTotal": this.waterDrunkTotal
                })
            }
        },
        
    }
</script>

<style lang="scss" scoped>

</style>