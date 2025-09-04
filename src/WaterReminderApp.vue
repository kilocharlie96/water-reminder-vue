<template>
    <header-vue></header-vue>
    <daily-goal v-if="!isGoalSet" @goal-is-set="isGoalSet = true"></daily-goal>
    <records-container v-if="isGoalSet"></records-container>

    <footer>
        <p>Created by <a id="link" href="https://github.com/kilocharlie96/water-reminder/">KiloCharlie96</a>.</p>
    </footer>
</template>

<script>
import HeaderVue from './components/Header-Vue.vue';
import DailyGoal from './components/DailyGoal.vue';
import RecordsContainer from './components/RecordsContainer.vue';

    export default {
        components: {
            HeaderVue,
            DailyGoal,
            RecordsContainer,
        },

        data() {
            return {
                isGoalSet: false,
            }
        },
    }
</script>

<style lang="scss" scoped>
</style>