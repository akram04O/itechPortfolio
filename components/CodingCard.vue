<template>
  <div class="card" ref="eventCard">
    <div class="front face">
      <div class="image-holder">
        <img :src="props.image"/>
      </div>
      <div class="details">
        <h1>
          {{ props.title }}
        </h1>
        <p class="description">
          {{ props.description }}
        </p>
      </div>
    </div>
    <div class="back face">
      <p>{{ props.backText }}</p>
    </div>
  </div>
</template>

<script setup>
// import VanillaTilt from 'vanilla-tilt'

// const eventCard = ref()

// onMounted(() => {
//   if(eventCard.value) VanillaTilt.init(eventCard.value, { max: 5, speed:200, glare: true })
// })

const props = defineProps({
  title : {
    type : String,
    // required : true
  },
  description : {
    type : String,
    // required : true
  },
  image : {
    type : String,
    // required : true
  },
  bimage : {
    type : String,
    // required : true
  },
  backText : {
    type : String,
    // required : true
  }
})


</script>

<style>
.card{
  text-align: center;
  width: 356px;
  border-radius: 10px;
  overflow: hidden;
}
.card:hover .front{
  transform: rotateY(-180deg);
}
.card:hover .back{
  transform: rotateY(0);
}
.face{
  transition: transform 1s;
  perspective: 1000px ;
  padding: 20px;
}
.back{
  backface-visibility: hidden;
  position: absolute;
  width: 100%;
  height: 100%;
  transform: rotateY(180deg);
  background-image: linear-gradient(135deg, #1C1C1C, #050505);

  padding: 20px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.back img{
  width: 200px;
  margin-bottom: 15px;
}
.front{
  backface-visibility: hidden;
  background-image: linear-gradient(135deg, #1C1C1C, #050505);
}
.image-holder{
  height: 250px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.details{
  color: white;

  & h1{
    font-family: 'IDGrotesk';
    font-size: 40px;
    
  }

  & .description{
    font-size: 15px;
    color: #8987A1;
  }
}
</style>