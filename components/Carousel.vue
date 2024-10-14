<template>
    <div class="w-full flex flex-auto items-center overflow-hidden relative perspective-400">
        <div v-for="(card, index) in props.cards" :key="index" ref="projectCards">
            <ProjectCard :image="card.image" :link="card.link"/>
        </div>
    </div>
</template>

<script setup lang="ts">

const props = defineProps({
    cards: {
        type: Array<{image: string, link: string | undefined}>,
        required: true
    }
})

const projectCards = ref<Array<HTMLElement>>()

const switchCarousel = (direction:string) => {
    if(direction === 'left') {
        let lastElem:HTMLElement|undefined = projectCards.value?.pop()
        if(lastElem) projectCards.value?.unshift(lastElem)
    }

    if(direction === 'right') {
        let lastElem:HTMLElement|undefined = projectCards.value?.shift()
        if(lastElem) projectCards.value?.push(lastElem)
    }

    if(projectCards.value && (projectCards.value?.length >= 4)) {
        projectCards.value?.forEach((item:HTMLElement, index:number)=>{
            item.classList.value = '';
            if(index === 0) {
                item.classList.add('carousel-hidden-item-left')
                item.onclick = null
            }
            else if(index === 1) {
                item.classList.add('carousel-left-item')
                item.onclick = ()=>switchCarousel('left')
            }
            else if(index === 2) {
                item.classList.add('carousel-mid-item')
                item.onclick = null
            }
            else if(index === 3) {
                item.classList.add('carousel-right-item')
                item.onclick = ()=>switchCarousel('right')
            }
            else if(index === 4) {
                item.classList.add('carousel-hidden-item-right')
                item.onclick = null
            }
            else item.classList.add('hidden','w-0','opacity-0')
        })
    }
    
}

onMounted(()=>{
    projectCards.value?.forEach((item:HTMLElement, index:number)=>{
        if(index === 0) {
            item.classList.add('carousel-hidden-item-left')
            item.onclick = null
        }
        else if(index === 1) {
            item.classList.add('carousel-left-item')
            item.onclick = ()=>switchCarousel('left')
        }
        else if(index === 2) {
            item.classList.add('carousel-mid-item')
            item.onclick = null
        }
        else if(index === 3) {
            item.classList.add('carousel-right-item')
            item.onclick = ()=>switchCarousel('right')
        }
        else if(index === 4) {
            item.classList.add('carousel-hidden-item-right')
            item.onclick = null
        }
        else item.classList.add('hidden','w-0','opacity-0')
    })
})

</script>

<style scoped>

</style>