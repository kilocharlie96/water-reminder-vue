<template>
  <div class="accordion">

    <button @click="isOpen = !isOpen" class="accordion-btn">
      {{ isOpen ? 'Zatvoriť' : 'Otvoriť' }}
    </button>

    <transition name="accordion">
      <div v-show="isOpen" class="accordion-content">
        <p>
          Toto je obsah akordeónu. Môžeš tu mať text, obrázky alebo aj iné Vue komponenty.
        </p>
      </div>
    </transition>
  </div>
</template>

<script setup>
const isOpen = false;
</script>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>

</style>