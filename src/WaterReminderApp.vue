<template>
    <header-vue></header-vue>
    <daily-goal v-if="!isGoalSet" @goal-is-set="isGoalSet = true"></daily-goal>
    <records-list v-if="isGoalSet"></records-list>


        <footer>
            <p>Created by <a id="link" href="https://github.com/kilocharlie96/water-reminder/">KiloCharlie96</a>.</p>
        </footer>
</template>

<script>
import HeaderVue from './components/Header-Vue.vue';
import DailyGoal from './components/DailyGoal.vue';
import NewRecordForm from './components/NewRecordForm.vue';
import RecordsList from './components/RecordsList.vue';

    export default {
        components: {
            HeaderVue,
            DailyGoal,
            NewRecordForm,
            RecordsList,
        },

        data() {
            return {
                waterDrankActual: 0,
                waterDrankDay: 0,
                isGoalSet: false,

                drinkingRecords: [],
            }
        },
    }
</script>

<style lang="scss" scoped>
</style>