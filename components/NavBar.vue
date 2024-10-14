<template>
    <header class="navbar">
      <div class="container">
        <div class="logo">
          <img src="../assets/logo/logo.png" alt="Logo" class="logo-image" />
        </div>
        <nav :class="['nav-links', { 'isMenuOpen': isMenuOpen }]">
          <a href="#" class="nav-item">Home</a>
          <a href="#" class="nav-item">About</a>
          <a href="#" class="nav-item">Projects</a>
          <a href="#" class="nav-item">Teams</a>
          <a href="#" class="nav-item">Leader</a>
          <button class="contact-btn">Contact Us</button>
        </nav>
        <!-- Hamburger icon for mobile -->
        <div class="hamburger" @click="toggleMenu">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
    </header>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isMenuOpen: false,
      };
    },
    methods: {
      toggleMenu() {
        this.isMenuOpen = !this.isMenuOpen;
      },
    },
  };
  </script>
  
  <style scoped>

  header {
    padding: 5px 10px;
  }
  .container {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 15px 20px;
    background-color: #000; /* dark background */
  }
  .logo {
    display: flex;
    align-items: center;
    margin-left: 20px;
  }
  .logo-image {
    height: 80px;
    width: 80px;
    margin-right: 10px;
  }
  .nav-links {
    display: flex;
    align-items: center;
  }
  .nav-links a{
    font-family: 'ItechSecondaryFont';
    font-size: 16px;
    font-weight: medium;
  }
  .nav-item {
    margin-right: 20px;
    color: #fff;
    text-decoration: none;
    font-size: 16px;
    padding: 10px;
  }
  .nav-item:hover {
    color: #8a8a8a;
  }
  .contact-btn {
    background-color: #6a00ff;
    color: #fff;
    padding: 10px 20px;
    border-radius: 20px;
    border: none;
    cursor: pointer;
    font-family: 'ItechFont';
    font-size: 16px;
    font-weight: regular;
    letter-spacing: 3px;
  }
  .contact-btn:hover {
    background-color: #5900e5;
  }
  
  /* Mobile styles */
  .hamburger {
    display: none;
    flex-direction: column;
    justify-content: space-between;
    height: 24px;
    cursor: pointer;
  }
  .hamburger span {
    display: block;
    height: 3px;
    width: 30px;
    background-color: #fff;
    border-radius: 5px;
  }
  
  /* Responsive */
  @media (max-width: 768px) {
    .nav-links {
      display: none;
    }
    .hamburger {
      display: flex;
    }
    .isMenuOpen {
      display: flex;
      flex-direction: column;
      position: absolute;
      top: 60px;
      left: 0;
      right: 0;
      background-color: #000;
      padding: 10px;
    }
    .nav-item {
      margin: 10px 0;
    }
  }
  </style>
  