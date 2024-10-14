<template>
  <div class="w-[1000px] aspect-video p-8  bg-[rgba(255,255,255,0.2)] border border-1 border-[rgba(255,255,255,0.2)] backdrop-blur-[60px] rounded-lg" ref="projectCard">
    <div class="relative w-full h-full flex items-center justify-center rounded-md overflow-hidden">
      <img :src="props.image" class="object-cover object-center"/>
    </div>
  </div>
</template>

<script lang="ts" setup>
import VanillaTilt from 'vanilla-tilt'

const props = defineProps({
  image: {
    type: String,
    required: true
  },
  link:{
    type: String,
    required: false
  }
})

const projectCard = ref<HTMLElement>()

onMounted(()=>{
  if(projectCard.value) VanillaTilt.init(projectCard.value, { max: 5, speed:200, glare: true })
})

</script>

<style>

</style>