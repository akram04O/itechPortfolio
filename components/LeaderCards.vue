<template>
  <div class="leaders-container">
    <div class="cards-container z-10">
      <div v-for="(item, index) in items" :key="index" 
            class="leader-card"
            @click="toggleCard(index)"
            :style="{ borderColor: borderColors[index] }"> <!-- Dynamically assign border colors -->
        <div class="card-content leader-front">
          <div class="leader-image-holder">
            <img :src="item.profileImage" alt="Profile Image" class="profile-image" />
          </div>
          <div class="card-text">
            <h2>{{ item.name }}</h2>
            <h3>{{ item.title }}</h3>
          </div>
        </div>
        <div class="card-content leader-back" :style="{backgroundColor: borderColors[index]}">
          <div class="back-card-text">
            <h2>{{ item.name }}</h2>
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
<script setup>
  import teamImage_ali from 'assets/images/team/ali.jpg'
  import teamImage_israa from 'assets/images/team/isra.jpg'
  import teamImage_akram from 'assets/images/team/akram.png'
  import teamImage_marwa from 'assets/images/team/marwa.png'
  import teamImage_yousra from 'assets/images/team/yousra.jpg'
  import teamImage_sirine from 'assets/images/team/Lina.jpg'
  import teamImage_douaa from 'assets/images/team/douaa.jpg'
  import teamImage_ismahan from 'assets/images/team/ismahane.jpg'
  import teamImage_rami from 'assets/images/team/rami.jpg'
// Unique border colors for each card
var borderColors = ['red', 'purple', 'violet', 'indigo', 'magenta', 'blue', 'teal', 'orange', 'green'];

 
  var items = [
  {
            name: "REMITA Ali Baghdadi",
            title: "Club president",
            profileImage: teamImage_ali,
            description: "Tech lover since childhood!  Turned that passion into a science Computer degree.  Joined i-Tech Club to meet Tech enthusiasts."
          },
          {
            name: "MEDJBOURI Ismahan",
            title: "Vice president",
            profileImage: teamImage_ismahan,
            description: "Tech lover since childhood!  Turned that passion into a science Computer degree.  Joined i-Tech Club to meet Tech enthusiasts."
          },
          {
            name: "MAZOUNI Marwa",
            title: "General Secretary",
            profileImage: teamImage_marwa,
            description: "My responsibilities include new member selection, performance, management, training planning, and resolving club relations issues."
          },
          {
            name: "Lina Sirine Abdellouche",
            title: "Human resources",
            profileImage: teamImage_sirine,
            description: "My responsibilities include new member selection, performance, management, training planning, and resolving club relations issues."
          },
          {
            name: "KEHAL Ali Ramy",
            title: "Human Resources Vice-Manager",
            profileImage: teamImage_rami,
            description: "My responsibilities include new member selection, performance, management, training planning, and resolving club relations issues."
          },
          {
            name: "KERROUT Israa",
            title: "Coding Leader",
            profileImage: teamImage_israa,
            description: "As a third-year CS student passionate about robotics, Arduino, web development, and CTFs."
          },
          {
            name: " KHEMIS Akram",
            title: "Robotics Leader",
            profileImage: teamImage_akram,
            description: "As a third-year CS student passionate about robotics, Arduino, web development, and CTFs."
          },
          {
            name: "Douaa Laouar",
            title: "Media Leader",
            profileImage: teamImage_douaa,
            description: "Tech lover since childhood!  Turned that passion into a science Computer degree.  Joined i-Tech Club to meet Tech enthusiasts."
          },
          
          {
            name: "ZATTOUTA Imene Yousra",
            title: "Organizing Leader",
            profileImage: teamImage_yousra,
            description: "Bac degree on Information systems and software engineering Coding team member Master 1 artificielle intelligence"
          },
          
  ]

  function selectElement(element){
    element.classList.add("expanded");
    element.classList.remove("blurred");
  }

  function diSelectElement(element){
    element.classList.remove("expanded");
    element.classList.add("blurred");
  }
  
  function toggleCard(index) {
    var cardsList = Array.from(document.getElementsByClassName("leader-card"));
    for(let card of cardsList){
      diSelectElement(card);
    }
    selectElement(cardsList[index])
  }
</script>
  
<style scoped>
  .leaders-container {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 20px;
  }
  
  .cards-container {
    display: grid;
    grid-template-columns: repeat(3, 500px); /* Adjusted for two rows */
    grid-gap: 10px;
    justify-items: center;
  }

  @media (width < 1200px) {
    .cards-container {
      grid-template-columns: 500px; /* Adjusted for two rows */
    }
  }
  
  .leader-card {
    overflow: hidden;
    position: relative;
    width: 300px;
    height: 300px;
    border: 3px solid;
    border-radius: 10px;
    text-align: center;
    transition: width 0.6s cubic-bezier(0.25, 0.1, 0.25, 1), 
                height 0.6s cubic-bezier(0.25, 0.1, 0.25, 1),
                translate 0.6s cubic-bezier(0.25, 0.1, 0.25, 1),
                transform 0.6s cubic-bezier(0.25, 0.1, 0.25, 1);
    cursor: pointer;
    display: flex;
    margin: 10px;
  }
  
  /* Expanded card styling */
  .leader-card.expanded {
    width: 600px;
  }
  
  /* Blur inactive cards */
  .leader-card.blurred .leader-image-holder{
    filter: blur(2px); /* Apply blur */
  }
  
  /* Profile image styling */
  .leader-image-holder {
    overflow: hidden;
    width: 150px;
    height: 150px;
    border: 3px solid;
    border-radius: 50%;
    transition: all 0.3s cubic-bezier(0.25, 0.1, 0.25, 1);
  }
  
  .leader-card.expanded .leader-image-holder {
    border: none;
    position: absolute;
    width: 300px;
    height: 100%;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    border-radius: 0%
  }

  .profile-image{
    width: 100%;
    place-content: center;
    object-fit: cover;

  }
  
  .card-content {
    overflow: hidden;
    width: 300px;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    transition: all 0.6s cubic-bezier(0.25, 0.1, 0.25, 1);
  }
  
  .card-content.leader-front{
    background-image: linear-gradient(135deg, #1C1C1C, #050505);
    z-index: 10;
  }
  
  .card-content.leader-back{
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    width: 300px;
    border-radius: 0 10px 10px 0;
    padding: 15px;
  }

  .leader-back .back-card-text{
    & h2{ /* leader name */
      font-family: 'IDGrotesk';
      font-size: 2rem;
    }
    & h3{ /* leader role */
      font-size: 1.5rem;
      opacity: 0.6;
      margin-block: 10px;
    }
  }

  
  .card-text {
    margin-left: 0;
    transition: margin-left 0.6s cubic-bezier(0.25, 0.1, 0.25, 1),
                opacity 0.6s cubic-bezier(0.25, 0.1, 0.25, 1);
  }
  
  .leader-card.expanded .card-text {
    display: none
  }
  
  .card-text h2{
    margin: 10px 0;
    font-family: 'IDGrotesk';
    font-size: 20px;
    color: #FFFFFF;
  }
  .card-text h3{
    font-family: 'IDGrotesk';
    font-size: 15px;
    color: #8987A1;
  }
</style>
