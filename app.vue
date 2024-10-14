<template>
  <div class="page w-full h-auto min-h-screen relative text-white">
    <div class="elipse -z-0"></div>
    <!-- Navbar section -->
    <Navbarsection class="font-grotesk font-regular z-1"/>
    <!-- home section -->
    <div class="sm:h-[90vh] h-[95vh] pt-14 relative">      
      <div class="glow-rectangle"></div>
      <div class="w-full absolute bottom-24 right-0 left-0">
        <img :src="team" class="w-full block object-fit team-i-tech" ref="iTechTeamImg"/>
      </div>
      <h6 class="font-grotesk  animate-typing overflow-hidden whitespace-nowrap border-r-8 border-r-white w-fit h-fit text-2xl sm:text-5xl md:text-6xl lg:text-7xl xl:text-8xl 2xl:text-9xl  text-center relative z-15 mx-auto tracking-wide">COMPILE YOUR FUTURE</h6>
      <div class="mt-[20vh] w-full flex justify-center">
    <h3 class="font-grotesk text-sm sm:text-lg text-center max-w-[80%] lg:max-w-[45%] mx-auto tracking-widest">
      Discover a scientific club specializing in computer science and robotics that allows students to develop and work on their skills
    </h3>
  </div>
      <div class="lavalamp-container absolute bottom-0 right-0 left-0 h-28 " style="background-color: red;background-image: linear-gradient(45deg, #62308f, #0666a7);">
        <div class="canvas">
          <div class="blur" id="balls-holder">
          </div>
          <div class="filter filter-dodge"></div>
          <div class="filter filter-burn"></div>
        </div>
      </div>
    </div>
    <!-- events section -->
    
    <!-- projects section -->
    <div class=" h-[100vh] pt-14 flex flex-col relative z-10 mb-20">
      <div class="w-fit mx-auto flex-none">
        <h1 class="section-title h-fit text-center text-5xl font-grotesk ">
          Check our work
        </h1>
        <p class="max-w-[1000px] text-center mt-24 md:mt-8 z-10 relative ">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit, accusamus. Iure, ab aliquam at minima eveniet numquam illum nisi suscipit laboriosam blanditiis aperiam deserunt.
        </p>
      </div>
      <Carousel :cards="projects"/>
    </div>
    <!-- coding section -->
    <div class="coding-section mb-20">
        <h1 class="section-title h-fit text-center text-5xl font-grotesk mt-5">
          Meet our teams
        </h1>
        <div class="coding-container">
          <CodingCard v-for="(item) in items" :title="item.title" :back-text="item.backText" :description="item.discription" :bimage="item.bimage" :image="item.image"/>
        </div>
    </div>
    <!-- Leaders section -->
     <div class="leaders-section mb-20">
        <h1 class="section-title h-fit text-center text-5xl font-grotesk mt-5">
          Meet our Leaders
        </h1>
        <LeaderCards/>
     </div>
    <!-- time line section -->
     <div class="timeline-section">
      <h1 class="section-title h-fit text-center text-5xl font-grotesk mt-5">
        Here's our History
      </h1>
      <div class="timeline-container">
        <div v-for="(timeLine) in timeLineInfo" class="timeline-card" :class="timeLine.direction">
          <div class="content">
            <div class="top">
              <h2 class="title">{{ timeLine.title }}</h2>
              <p>{{ timeLine.date }}</p>
            </div>
            <div class="text-holder">
              <p class="text">{{ timeLine.text }}</p>
            </div>
          </div>
          <div class="circle-glow"></div>
        </div>
      </div>
     </div>
     <!--Servey section-->
     <div class="survey-section mb-20">
      <ServeyComponent />
     </div>
    <!-- footer section -->
    <div class="footer-section mb-20">
        <FOOTER/>
     </div>
  </div>
</template>

<script setup >
import Navbar from './components/Navbarsection.vue'
import team from './assets/i-tech-team/club-members.png'
import VanillaTilt from 'vanilla-tilt'
import codingImg from "./assets/images/coding.jpg"
import projectImage from './assets/projects/ai.jpg'
import projectImage2 from './assets/projects/coding.jpg'
import projectImage3 from './assets/projects/cyber.jpg'
import projectImage4 from './assets/projects/robotic.jpg'

// coding images
import codingImageCoding from './assets/images/coding/coding.png'
import codingImageOrga from './assets/images/coding/orga.png'
import codingImageDesign from './assets/images/coding/design.png'
import codingImageRobotic from './assets/images/coding/robotic.png'
import codingImageMedia from './assets/images/coding/media.png'

import leaderImage_khalil from './assets/images/coding leaders/khalil.png'
import leaderImage_marwa from './assets/images/coding leaders/marwa.png'
import ServeyComponent from './components/ServeyComponent.vue'
// coding images

const iTechTeamImg = ref()

const projects = ref([
  {image:projectImage,link:undefined},
  {image:projectImage2,link:undefined},
  {image:projectImage3,link:undefined},
  {image:projectImage4,link:undefined},
  {image:projectImage,link:undefined},
  {image:projectImage2,link:undefined},
  {image:projectImage3,link:undefined},
  {image:projectImage4,link:undefined},
  {image:projectImage,link:undefined},
  {image:projectImage2,link:undefined},
  {image:projectImage3,link:undefined},
  {image:projectImage4,link:undefined},
])

onMounted(() => {
  if(iTechTeamImg.value) VanillaTilt.init(iTechTeamImg.value, { max: 2, speed:200, glare: true })
})

// coding cards info
var items =  [
    {
        title: "Organizing",
        image: codingImageOrga,
        discription: "Take a look at some of our recent projects...",
        bimage: leaderImage_khalil,
        backText: "AI-related projects and innovations...",
    },
    {
        title: "Coding",
        image: codingImageCoding,
        discription: "Take a look at some of our recent projects...",
        bimage: leaderImage_khalil,
        backText: "Coding projects and solutions...",
    },
    {
        title: "Robotic",
        image: codingImageRobotic,
        discription: "Take a look at some of our recent projects...",
        bimage: leaderImage_khalil,
        backText: "Robotic projects and advancements...",
    },
    {
        title: "Design",
        image: codingImageDesign,
        discription: "Take a look at some of our recent projects...",
        bimage: leaderImage_khalil,
        backText: "Design projects and creativity...",
    },
    {
        title: "Media",
        image: codingImageMedia,
        discription: "Take a look at some of our recent projects...",
        bimage: leaderImage_marwa,
        backText: "Media projects and innovations...",
    },
];
// coding cards info

// timeline info
var timeLineInfo = [
  {
    date: "2019",
    title: "Ready Bootcamp",
    text: "It is an educational camp, representing the first initiative of its kind in Algeria. A group of Algerian doctors residing abroad initiated this camp, offering diverse lectures in various fields such as artificial intelligence, programming, startups, and leadership.",
    direction: "left",
  },
  {
    date: "2020",
    title: "Ai Vertual Camp",
    text: "Through this initiative, a group of Algerian doctors presented diverse lectures in the field of artificial intelligence. The goal was to explore how machines can be used to find real solutions in various domains.",
    direction: "right",
  },
  {
    date: "2021",
    title: "Ai Fest",
    text: "It involved a series of diverse lectures in the field of artificial intelligence at the university level, presented by specialists in the field.",
    direction: "left",
  },
  {
    date: "2022",
    title: "ProPath",
    text: "The club organized an exhibition for innovation and new technologies to promote an entrepreneurial culture and redirect students towards investment opportunities, as well as to embrace small, medium, and startup companies.",
    direction: "right",
  },
  {
    date: "2023",
    title: "DIC",
    text: "A competition and lecture series in the field of robotics were organized by the club, targeting students, graduates, and project owners in the robotics and controllers domain, fostering competition for the title.",
    direction: "left",
  },
]
// timeline info

/* lavalamp balls */
function getRandomNum(start, end){
  return Math.floor(Math.random() * (end - start)) + start;
}

function createBallElement(left, top, radius){
  const element = document.createElement("div");
  element.className = "lavalamp-circle";
  element.style.left = `${left}px`;
  element.style.top = `${top}px`;
  element.style.width = `${radius}px`;
  element.style.height = `${radius}px`;
  element.style.borderRadius = `50%`;
  element.style.position = 'absolute'
  element.style.backgroundColor = '#5227FF'
  return element;
}

onMounted(()=>{
  const ballsHolder= document.getElementById("balls-holder");

  let width = ballsHolder.clientWidth;
  let height = ballsHolder.clientHeight;

  window.addEventListener("resize", ()=>{
    width = ballsHolder.clientWidth;
    height = ballsHolder.clientHeight;
  })
  
  let numberOfBalls = 20;
  let radius = 120;

  let ballsArr = [];

  // generate balls
  for(let i = 0; i < numberOfBalls; i++){
    let ball = {
      x: getRandomNum(1, width),
      y: getRandomNum(1, height),
      dx: getRandomNum(-8, 8) || 5,
      dy: getRandomNum(-8, 8) || 5,
      element: null,
    };
    ballsArr.push(ball);

    ball.element = createBallElement(ball.x, ball.y, radius);

    ballsHolder.appendChild(ball.element);
  }

  function checkBounce(ball){
    if(ball.x > width && ball.dx > 0){
      ball.dx *= -1;
    }
    if(ball.x < -radius && ball.dx < 0){
      ball.dx *= -1;
    }
    if(ball.y > height && ball.dy > 0){
      ball.dy *= -1;
    }
    if(ball.y < -radius && ball.dy < 0){
      ball.dy *= -1;
    }
  }

  function updateElementPos(ball){
    ball.x += ball.dx * 0.2;
    ball.y += ball.dy * 0.2;

    checkBounce(ball);

    ball.element.style.left = `${ball.x}px`;
    ball.element.style.top = `${ball.y}px`;
  }


  setInterval(()=>{
    for(const ball of ballsArr){
      updateElementPos(ball);
    }
  }, 10)
})

/* lavalamp balls */

</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}

@font-face {
        font-family: ItechRegular;
        src: url(../fonts/itech-Regular.ttf) format("ttf");
    }

.page{
  background-color: black;
}
.section-title{
  position: relative;
  z-index: 0;
  margin-bottom: 50px;
}
.section-title::before{
  content: "";
  position: absolute;
  left: 50%;
  top: 50%;

  width: 700px;
  height: 200px;
  border-radius: 50%;
  filter: blur(150px);
  transform: translate(-50%, -50%);

  z-index: -1;

  background-color: #5227FF;
}

/* Lava lamp section */
.lavalamp-container{
  background-color: red;
  background-image: linear-gradient( #5227FF, #00A3FF);
}

.canvas {
  top: 10px; left: 10px; right: 10px; bottom: 10px;
  position: absolute;
  background:black;
  overflow:hidden;
}

.blur {
  filter:blur(40px);
  height: 100%;
}

.filter {
  pointer-events: none;
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
}

.filter-dodge {
  background: #808080;
  mix-blend-mode: color-dodge;
}

.filter-burn {
  background: black;
  mix-blend-mode: color-burn;
}

.lavalamp-circle {
  position: absolute;
  display:block;
  width:200px;
  aspect-ratio: 1 / 1;
  background: #ff5100;
  border-radius:100%;
  margin-bottom: 10px;
}
/* Lava lamp section */

.coding-cards{
  z-index: 10;
  position: relative;
}

.glow-rectangle{
  position: absolute;
  width: 120%;
  height: 298px;
  left: -133px;
  top: 50%;
  transform: translateY(-50%);
  
  background: linear-gradient(88.7deg, #D14FFF 1.11%, #00A3FF 83.13%);
  mix-blend-mode: screen;
  filter: blur(139px);
  border-radius: 193px;
}

.team-i-tech {
  -webkit-filter: drop-shadow(4px 4px 0 rgb(255, 255, 255))
                  drop-shadow(-4px -4px 0 rgb(255, 255, 255));
  filter: drop-shadow(4px -4px 0 rgb(255, 255, 255)) 
          drop-shadow(-4px -4px 0 rgb(255, 255, 255));
}

/* coding section ############################## */
.coding-section{
  position: relative;
  z-index: 10;
}

.coding-container{
  max-width: 1500px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 50px;
  margin-inline: auto;
}
/* coding section ############################## */

/* time line section ############################## */

/* The actual timeline (the vertical ruler) */
.timeline-container {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
}

/* The actual timeline (the vertical ruler) */
.timeline-container::after {
  content: '';
  position: absolute;
  width: 6px;
  background-color: white;
  top: 20px;
  bottom: 20px;
  left: 50%;
  margin-left: -3px;
}

/* Container around content */
.timeline-card {
  padding: 10px 40px;
  position: relative;
  background-color: inherit;
  width: 50%;
  border: 3px solid #272eff;

  &.left{
    border-radius: 30px 0 0 30px;
  }
  &.right{
    border-radius: 0 30px 30px 0;
  }
}

/* The circles on the timeline */
.timeline-card::after {
  content: '';
  position: absolute;
  width: 25px;
  height: 25px;
  right: -16px;
  background-color: white;
  border: 4px solid #5227FF;
  top: 15px;
  border-radius: 50%;
  z-index: 2;
}

.timeline-card .circle-glow{
  position: absolute;
  width: 30px;
  height: 30px;
  right: -15px;
  background-color: #5227FF;
  top: 12.5px;
  border-radius: 50%;
  z-index: 1;
  scale: 2;
  filter: blur(10px);
  opacity: 0;
  transition: opacity .5s;
}

.timeline-card:hover .circle-glow{
  opacity: 1;
}

/* Fix the circle glow for containers on the right side */
.right .circle-glow {
  left: -15px;
}

.timeline-card .top{
  display: flex;
  justify-content: space-between;
}

.timeline-card .text-holder{
  display: grid;
  grid-template-rows: 0fr;
  transition: grid-template-rows .3s;
}

.timeline-card:hover .text-holder{
  grid-template-rows: 1fr;
}

.timeline-card .text{
  overflow: hidden;
}

/* Place the container to the left */
.left {
  left: 0;
}

/* Place the container to the right */
.right {
  left: 50%;
}

/* Add arrows to the left container (pointing right) */
.left::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  right: 30px;
  border: medium solid white;
  border-width: 10px 0 10px 10px;
  border-color: transparent transparent transparent white;
}

/* Add arrows to the right container (pointing left) */
.right::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  left: 31px;
  border: medium solid white;
  border-width: 10px 10px 10px 0;
  border-color: transparent white transparent transparent;
}

/* Fix the circle for containers on the right side */
.right::after {
  left: -15px;
}

/* The actual content */
.content {
  color: rgb(255, 255, 255);
  padding: 20px 30px;
  background-color: rgb(0, 0, 0);
  box-shadow: 0px -5px 25px #5227FF;
  position: relative;
  border-radius: 6px;
}

.content .title{
  font-family: 'IDGrotesk';
  font-size: 1.25rem;
}
.content .top p{
  font-family: 'IDGrotesk';
}

/* Media queries - Responsive timeline on screens less than 600px wide */
@media screen and (max-width: 600px) {
  /* Place the timelime to the left */
  .timeline-container::after {
    left: 28px;
  }
  
  /* Full-width containers */
  .timeline-card {
    width: 100%;
    padding-left: 70px;
    padding-right: 25px;
  }
  
  /* Make sure that all arrows are pointing leftwards */
  .timeline-card::before {
    left: 60px;
    border: medium solid white;
    border-width: 10px 10px 10px 0;
    border-color: transparent white transparent transparent;
  }

  /* Make sure all circles are at the same spot */
  .left::after, .right::after {
  left: 15px;
  }
  
  /* Make all right containers behave like the left ones */
  .right {
  left: 0%;
  }
}
/* time line section ############################## */


</style>
