<script setup>
import HarryPottersCards from "./HarryPottersCards.vue";

</script>

<template>
  <Suspense>
    <template #default>
      <HarryPottersCards />
    </template>
    <template #fallback>
      <div class="cards">
        <NSpin size="large" />
      </div>
    </template>
  </Suspense>
</template>

<style scoped>
.cards {
  height: 700px;
  background-color: rgb(27, 26, 26);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>