<template>
    <h3>Aký je tvoj dnešný cieľ?</h3>
    <form @submit.prevent="setGoal">
        <input type="number" step="0.1" v-model="dailyGoal" autofocus> litrov
    </form>

    <recommended-amount>
        <small>
            <p>Odporúčaná denná dávka je od 2 do 3 litrov vody. Presnejšie 0,5 litra na každých 15 kg hmotnosti.</p>
            <p>To znamená, že človek s hmotnosťou 80 kg by mal vypiť cca 2,5l tekutín denne.</p>
            <p><em>Uvádzané pre optimálnu dennú záťaž. Teda bez športových aktivít, bez vonkajších tropických teplôt, ...</em></p>
        </small>
    </recommended-amount>


    <weight-form :class="{ hidden: weightSet == true }">
        <p>Ak chceš, pomôžem Ti orientačne vypočítať optimálnu denú dávku vody podľa tvojej váhy.</p>
        <h3>Aká je tvoja váha?</h3>
        <form @submit.prevent="setGoal">
            <input @input="countGoalByWeight" type="number" v-model="bodyWeight"> kg.
        </form>
    </weight-form>
    
</template>

<script>
    export default {
        data() {
            return {
                dailyGoal: 0.0,
                bodyWeight: 0,
                goalByWeight: 0,
                weightSet: false
            }
        }, 
        methods: {
            setGoal(){
                this.$emit('goal-is-set', this.dailyGoal)
            },
            countGoalByWeight() {
                this.dailyGoal = Number(((this.bodyWeight / 15) * 0.5).toFixed(1));
            }
        },
    }
</script>

<style lang="scss" scoped></style>