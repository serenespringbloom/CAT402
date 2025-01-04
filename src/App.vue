<script setup>
import { RouterView } from 'vue-router';
import TheWelcome from './views/TheWelcome.vue';
</script>

<script>
export default {
  mounted() {
    // Add smooth scrolling to all anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();

        const targetId = this.getAttribute('href').substring(1); // Remove "#" from href
        const targetElement = document.getElementById(targetId);

        if (targetElement) {
          const headerHeight = document.querySelector('header').offsetHeight; // Fixed header height
          const targetPosition = targetElement.offsetTop - headerHeight;

          window.scrollTo({
            top: targetPosition,
            behavior: 'smooth',
          });
        }
      });
    });
  },
};
</script>

<template>
  <header class="site-header">
    <div class="header-content">
      <h1 class="logo">
        <img src="./assets/images/logo2.png">
        <!-- <a href="#">meowchandise.my</a> -->
      </h1>
      <nav class="nav-menu">
        <a href="#">Home</a>
        <a href="#custom-merch">Products</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <div class="wrapper">
    <TheWelcome />
  </div>

  <footer class="footer">
      <div class="footer-container">
        <!-- Brand and About -->
        <div class="footer-brand">
          <h3>Meowchandise.my</h3>
          <p>Your one-stop shop for everything feline. Join our community of cat lovers today!</p>
        </div>

        <!-- Quick Links -->
        <div class="footer-links">
          <h4>Quick Links</h4>
          <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#custom-merch">Products</a></li>
            <li><a href="#about">About Us</a></li>
            <li><a href="#contact">Contact Us</a></li>
          </ul>
        </div>

        <!-- Social Media -->
        <div class="footer-social">
          <h4>Follow Us</h4>
          <div class="social-icons">
            <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
            <a href="https://www.facebook.com" target="_blank" aria-label="Facebook">
              <i class="fa fa-facebook"></i>
            </a>
            <a href="https://www.instagram.com" target="_blank" aria-label="Instagram">
              <i class="fa fa-instagram"></i>
            </a>
            <a href="https://www.twitter.com" target="_blank" aria-label="Twitter">
              <i class="fa fa-twitter"></i>
            </a>
            <a href="https://www.youtube.com" target="_blank" aria-label="YouTube">
              <i class="fa fa-youtube"></i>
            </a>
          </div>
        </div>
      </div>

      <!-- Bottom Bar -->
      <div class="footer-bottom">
        <p>&copy; 2025 Meowchandise.my. All rights reserved.</p>
        <p>Made with ❤️ for cat lovers everywhere.</p>
      </div>
    </footer>
</template>

<style scoped>
html {
  scroll-behavior: smooth;
}

section {
  scroll-margin-top: 80px; /* Adjust to match the header height */
}
/* Header Styles */
.site-header {
  background: linear-gradient(to right, #f7e6da, #f3c677);
  padding: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  position: sticky; /* Keeps the header fixed on scroll */
  top: 0;
  z-index: 1000;
}

.header-content {
  max-width: 1300px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px; /* Adds spacing between the image and the text */
}

.logo img {
  width: auto; /* Adjust size based on your logo image */
  height: 75px; /* Adjust size based on your logo image */
  border-radius: 15%; /* Optional: makes the logo circular */
  transition: transform 0.3s ease; /* Animation for hover effect */
}

.logo img:hover {
  transform: scale(1.1); /* Slight zoom effect on hover */
}

.nav-menu {
  display: flex;
  gap: 20px;
}

.nav-menu a {
  font-size: 1.2rem;
  color: #fff;
  text-decoration: none;
  font-weight: bold;
  padding: 10px 15px;
  border-radius: 5px;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.nav-menu a:hover {
  background-color: rgba(255, 255, 255, 0.2);
  transform: scale(1.1);
}

/* Mobile Menu */
@media (max-width: 768px) {
  .header-content {
    flex-direction: column;
    gap: 10px;
  }

  .nav-menu {
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
  }

  .nav-menu a {
    font-size: 1rem;
  }
}

nav {
  margin-top: 10px;
}

nav a {
  color: #fff;
  text-decoration: none;
  margin: 0 15px;
  font-weight: bold;
}

/* Footer Section */
.footer {
  background-color: #333;
  color: #f9f9f9;
  padding: 40px 20px;
  text-align: center;
}

.footer-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: flex-start;
  gap: 20px;
  max-width: 1200px;
  margin: 0 auto;
}

.footer-brand {
  flex: 1;
  min-width: 250px;
}

.footer-brand h3 {
  font-size: 1.8rem;
  color: #ff6f61;
  margin-bottom: 10px;
}

.footer-brand p {
  font-size: 1rem;
  line-height: 1.6;
  color:#a0a0a0;
}

.footer-links {
  flex: 1;
  min-width: 200px;
}

.footer-links h4 {
  font-size: 1.4rem;
  margin-bottom: 15px;
  color: #ff6f61;
}

.footer-links ul {
  list-style: none;
  padding: 0;
}

.footer-links ul li {
  margin: 8px 0;
}

.footer-links ul li a {
  color: #f9f9f9;
  text-decoration: none;
  font-size: 1rem;
  transition: color 0.3s ease;
}

.footer-links ul li a:hover {
  color: #ff6f61;
}

.footer-social {
  flex: 1;
  min-width: 200px;
}

.footer-social h4 {
  font-size: 1.4rem;
  margin-bottom: 15px;
  color: #ff6f61;
}

.social-icons {
  display: flex;
  justify-content: center;
  gap: 15px;
}

.social-icons a {
  color: #f9f9f9;
  font-size: 1.5rem;
  transition: color 0.3s ease, transform 0.3s ease;
}

.social-icons a:hover {
  color: #ff6f61;
  transform: scale(1.1);
}

.footer-bottom {
  margin-top: 30px;
  border-top: 1px solid #555;
  padding-top: 15px;
  font-size: 0.9rem;
  color: #aaa;
}

.footer-bottom p{
  color:#a0a0a0;
}

/* Responsive Design */
@media (max-width: 768px) {
  .footer-container {
    flex-direction: column;
    align-items: center;
  }

  .footer-links ul {
    text-align: center;
  }

  .footer-social {
    text-align: center;
  }
}

</style>
