<template>
  <div class="w-[300px] md:w-[550px] aspect-square rounded-[25px] relative overflow-hidden cursor-pointer" ref="eventCard">
    <div class="z-10 text-white absolute bottom-8 right-8 left-8">
      <h1 class="text-3xl font-bold">
        {{ props.title }}
      </h1>
      <p class="truncate">
        {{ props.description }}
      </p>
      <h3>
        {{ props.date }}
      </h3>
    </div>
    <div class="absolute top-0 right-0 bottom-0 left-0 z-0">
      <img :src="props.image" class="object-cover object-center w-full h-full blur-sm hover:blur-none hover:scale-125 transition-all duration-200 " />
    </div>
  </div>
</template>

<script lang="ts" setup>
import VanillaTilt from 'vanilla-tilt'

const eventCard = ref<HTMLElement>()

onMounted(() => {
  if(eventCard.value) VanillaTilt.init(eventCard.value, { max: 5, speed:200, glare: true })
})

type cardInfos = {
  title : string,
  description : string,
  date : string,
  image : string
}

const props = defineProps({
  title : {
    type : String,
    // required : true
  },
  description : {
    type : String,
    // required : true
  },
  date : {
    type : String,
    // required : true
  },
  image : {
    type : String,
    // required : true
  }
})


</script>

<style>
</style>