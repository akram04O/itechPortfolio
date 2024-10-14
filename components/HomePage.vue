<template>
    <div class="container">
      <h1 class="headline">COMPILE YOUR FUTURE</h1>
      <p class="sub-headline">
        Discover a scientific club specializing in computer science and robotics
        that allows students to develop and work on their skills
      </p>
      <div class="group-image">
        <img src="../assets/i-tech-team/club-members.png" alt="Group of Students" />
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CompileYourFuture',
  };
  </script>
  
  <style scoped>

  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    width: 100%;
    margin: 0 auto;
  }
  
  .headline {
    font-family: 'ItechFont';
    font-size: 70px;
    font-weight: normal;
    letter-spacing: 5px;
    text-shadow: 0 -10px 33px #F1E4E4;
    margin-bottom: 20px;
  }
  
  .sub-headline {
    font-size: 16px;
    font-weight: normal;
    margin-bottom: 40px;
    max-width: 700px;
    line-height: 1.5;
  }
  
  .group-image img {
    width: 100%;
    height: auto;
  }
    
  /* Responsive styles */
  @media (max-width: 768px) {
    .headline {
      font-size: 2.5rem;
    }
  
    .sub-headline {
      font-size: 1rem;
      margin-bottom: 30px;
    }
  }
  
  @media (max-width: 480px) {
    .headline {
      font-size: 2rem;
    }
  
    .sub-headline {
      font-size: 0.9rem;
    }
  }
  </style>
  