<script setup>
  import HarryPotterCards from "./components/HarryPotterCardsSuspense.vue";
  import RickMortyCards from "./components/RickMortyCards.vue";
  import Hero from "./components/Hero.vue";
  import {ref} from "vue";

  const isHarryPotter = ref(true);
</script>

<template>
  <main>
    <Hero
        :isHarryPotter="isHarryPotter"
        @selectShow="isHarryPotter = !isHarryPotter"
    />
<!--    <HarryPotterCards v-if="isHarryPotter" />-->
<!--    <RickMortyCards v-else />-->
    <!-- This is the same that two components above -->
<!--    <Component :is="isHarryPotter ? HarryPotterCards : RickMortyCards" />-->
    <!-- But this time we can maintain component state -->
    <KeepAlive>
      <Component :is="isHarryPotter ? HarryPotterCards : RickMortyCards" />
    </KeepAlive>
  </main>
</template>