<template>
  <recommended-amount>
    <small>
      <div v-for="(p, i) in paragraphs" :key="i">
        <button @click="toggle(i)">
          {{ opened === i ? "−" : "+" }} Koľko vody
        </button>

        <transition name="accordion">
          <p v-if="opened === i">{{ p }}</p>
        </transition>
      </div>
    </small>
  </recommended-amount>
</template>

<script>
    export default {
        data() {
            return {
                dailyGoal: 0.0,
                bodyWeight: 0,
                goalByWeight: 0,
                weightSet: false,
                opened: null,
                paragraphs: [
                    "Odporúčaná denná dávka je od 2 do 4 litrov vody. Presnejšie 0,5 litra na každých 15 kg hmotnosti.",
                    "To znamená, že človek s hmotnosťou 80 kg by mal vypiť cca 2,5l tekutín denne.",
                    "Uvádzané pre optimálnu dennú záťaž. Teda bez športových aktivít, bez vonkajších tropických teplôt, ..."
                ]
            }
        }, 
        methods: {
            toggle(i) {
            this.opened = this.opened === i ? null : i
            },
            setGoal(){
                this.$emit('goal-is-set', this.dailyGoal)
            },
            countGoalByWeight() {
                this.dailyGoal = Number(((this.bodyWeight / 15) * 0.5).toFixed(1));
            }
        },
    }
</script>

<style>
    .accordion-enter-active,
    .accordion-leave-active {
    transition: all 0.3s ease;
    }
    .accordion-enter-from,
    .accordion-leave-to {
    opacity: 0;
    max-height: 0;
    overflow: hidden;
    }
</style>