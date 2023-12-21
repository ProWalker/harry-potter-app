<script setup>
  import {defineProps} from 'vue'

  const {image, name} = defineProps([
      'image',
      'name',
  ])
  let default_image
  if (!image) {
    // console.log(`Image for ${name} is empty`)
    default_image = '/src/assets/no_image.png'
    // console.log(default_image)
  }
</script>

<template>
  <NCard>
    <template #cover>
      <img v-if="default_image" :src="default_image">
      <img v-if="image" :src="image">
    </template>
    <h3>{{ name }}</h3>
<!--    <div class="members">-->
<!--      <p-->
<!--          v-for="(member, index) in family_members"-->
<!--          :key="member"-->
<!--      >-->
<!--        <span class="member">{{member}}<span v-if="index < family_members.length - 1">,&nbsp</span></span>-->
<!--      </p>-->
<!--    </div>-->
    <slot></slot>
  </NCard>
</template>

<style scoped>
.n-card {
  width: 200px;
  margin: 10px 20px;
  min-height: 400px;
}
.n-card img {
  height: 250px
}
</style>