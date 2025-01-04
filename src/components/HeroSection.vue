<template>
    <div class="hero">
      <video autoplay muted loop playsinline class="video-bg">
        <source src="@/assets/videos/hero-bg.mp4" type="video/mp4" />
        <!-- Ensure the video file is in the correct path -->
      </video>
      <div class="hero-content">
        <h1>Welcome to Meowchandise.my</h1>
        <p>Design Your Dream Merch or Shop Our Cat-Inspired Collection!</p>
        <button class="cta-button">Shop Now</button>
        <button class="cta-button secondary" @click="scrollToCustomMerch">Design Your Own Merch</button>
      </div>
      <!-- Scroll Indicator -->
      <a href="#about" class="scroll-indicator" aria-label="Scroll to About Us">
        <span class="arrow"></span>
      </a>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      scrollToCustomMerch() {
        const element = document.getElementById("custom-merch");
        if (element) {
          element.scrollIntoView({ behavior: "smooth" });
        } else {
          console.error("Element with ID 'custom-merch' not found.");
        }
      },
    },
    mounted() {
      // Scroll functionality for anchor links
      document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
        anchor.addEventListener("click", (e) => {
          e.preventDefault();
  
          const targetId = anchor.getAttribute("href").substring(1);
          const targetElement = document.getElementById(targetId);
  
          if (targetElement) {
            const headerHeight = document.querySelector("header")?.offsetHeight || 0;
            const targetPosition = targetElement.offsetTop - headerHeight;
  
            window.scrollTo({
              top: targetPosition,
              behavior: "smooth",
            });
          } else {
            console.error(`Element with ID '${targetId}' not found.`);
          }
        });
      });
    },
  };
  </script>
  
  <style scoped>
  /* Hero Section */
  .hero {
    position: relative;
    height: 70vh; /* Reduced height for better visibility */
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: #fff;
    overflow: hidden;
  }
  
  .hero::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(to bottom, rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.7));
    z-index: -1;
  }
  
  .video-bg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: -1;
    opacity: 0.7;
  }
  
  .hero-content {
    z-index: 1;
    max-width: 600px;
    padding: 20px;
    background: rgba(0, 0, 0, 0.5);
    border-radius: 10px;
    animation: fadeIn 2s ease-in-out;
  }
  
  .hero h1 {
    font-size: 2.5rem;
    margin-bottom: 10px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  }
  
  .hero p {
    font-size: 1.2rem;
    margin-bottom: 20px;
    color: #f5f5f5;
  }
  
  .cta-button {
    padding: 15px 30px;
    font-size: 1rem;
    font-weight: bold;
    color: #fff;
    background-color: #ff6f61;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.3s ease;
  }
  
  .cta-button:hover {
    background-color: #ec5a50;
    transform: scale(1.05);
  }
  
  /* Scroll Indicator */
  .scroll-indicator {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    width: 50px;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(0, 0, 0, 0.5);
    border-radius: 50%;
    cursor: pointer;
    animation: bounce 2s infinite;
  }
  
  .arrow {
    display: block;
    width: 16px;
    height: 16px;
    border: 3px solid #fff;
    border-left: transparent;
    border-top: transparent;
    transform: rotate(45deg);
  }
  
  /* Bounce Animation */
  @keyframes bounce {
    0%, 20%, 50%, 80%, 100% {
      transform: translateY(0);
    }
    40% {
      transform: translateY(10px);
    }
    60% {
      transform: translateY(5px);
    }
  }
  
  /* Responsive Adjustments */
  @media (max-width: 768px) {
    .hero {
      height: 60vh;
    }
  
    .hero h1 {
      font-size: 2rem;
    }
  
    .hero p {
      font-size: 1rem;
    }
  
    .cta-button {
      font-size: 0.9rem;
      padding: 10px 20px;
    }
  
    .scroll-indicator {
      width: 40px;
      height: 40px;
    }
  
    .arrow {
      width: 12px;
      height: 12px;
    }
  }
  </style>
  