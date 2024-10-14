<template>
  <nav class="w-full flex items-center justify-between relative h-[5vh] sm:h-[10vh] px-6 py-0 sm:px-16">

      <div class="md:w-[8%] w-[16%]">
        <img :src="i_tech_logo" class="w-full block object-fit"/>
      </div>

      <Icon :name="menuIsOpened ? 'ic:round-close' : 'ic:round-menu'" class="sm:w-0 sm:h-0 w-6 h-6" color="white" @click="menuIsOpened = !menuIsOpened"/>

      <ul :class="menuIsOpened ? 'menu-bar' : 'menu-bar-closed'">
        <li class="w-full h-full sm:w-auto sm:h-auto py-2 sm:py-0 cursor-pointer relative">
          <a class="w-full h-full sm:w-auto sm:h-auto text-center block hover-underline">Home</a>
        </li>
        <li class="w-full h-full sm:w-auto sm:h-auto py-2 sm:py-0 cursor-pointer relative">
          <a class="w-full h-full sm:w-auto sm:h-auto text-center block hover-underline">Projects</a>
        </li>
        <li class="w-full h-full sm:w-auto sm:h-auto py-2 sm:py-0 cursor-pointer relative">
          <a class="w-full h-full sm:w-auto sm:h-auto text-center block hover-underline">Teams</a>
        </li>
        <li class="w-full h-full sm:w-auto sm:h-auto py-2 sm:py-0 cursor-pointer relative">
          <a class="w-full h-full sm:w-auto sm:h-auto text-center block hover-underline">Leaders</a>
        </li>
        <li class="w-full h-full sm:w-auto sm:h-auto py-2 sm:py-0 cursor-pointer relative">
          <a class="w-full h-full sm:w-auto sm:h-auto text-center block hover-underline">TimeLine</a>
        </li>
        
        <li class="hidden sm:block">
          <button class="group relative m-1 cursor-pointer overflow-hidden rounded-full border-2 border-white imp-btn">
            <span class="ease absolute top-1/2 h-0 w-64 origin-center -translate-x-20 rotate-45 bg-[#5E25FF] transition-all duration-300 group-hover:h-64 group-hover:-translate-y-32"></span>
            <span class="ease relative transition duration-300 group-hover:text-white">Contact Us</span>
          </button> 
        </li>
      </ul>
      

  </nav>
</template>

<script lang="ts" setup>
import i_tech_logo from "../assets/logo/logo.png"

const { width } = useWindowSize()

const menuIsOpened = ref<boolean>(false)

onMounted(()=>{
  if(width.value > 640) menuIsOpened.value = true 
  else {menuIsOpened.value = false}

  watch(width,(val:number)=>{
    if(val > 640) menuIsOpened.value = true
  })
})

</script>

<style scoped>
.hover-underline::after {
  content: '';
  display: block;
  width: 0;
  height: 2px;
  background: #ffffff;
  transition: width 0.3s;
  position: absolute;
  bottom: 0;
  left: 0;
}

.hover-underline:hover::after {
  width: 100%;
}

</style>


