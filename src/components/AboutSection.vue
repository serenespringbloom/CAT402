<template>
    <section class="about" id="about">
      <h2>About Us</h2>
      <div class="about-content">
        <img src="../assets/images/dp.png" alt="About Us" class="about-image" />
        <div class="about-text">
          <p>
            Meowchandise.my is your go-to destination for all things cat! Our
            mission is to bring joy to cat lovers everywhere with high-quality,
            adorable merchandise designed for both you and your furry friends.
          </p>
          <p>
            We are passionate about celebrating the special bond between humans
            and cats. From stylish cat-themed apparel to functional everyday
            items, we ensure every product is crafted with care and love for all
            cat enthusiasts.
          </p>
          <p>
            Join our community of cat lovers today and discover why
            Meowchandise.my is the "purr-fect" place for you!
          </p>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "AboutSection",
  };
  </script>
  
  <style scoped>
  .about {
    background-color: #f9f6f2;
    padding: 60px 20px;
    text-align: center;
    color: #333;
  }
  
  .about h2 {
    font-size: 2.5rem;
    color: #ff6f61;
    margin-bottom: 20px;
  }
  
  .about-content {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 20px;
    max-width: 1200px;
    margin: 0 auto;
  }
  
  .about-image {
    max-width: 300px;
    border-radius: 50%;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }
  
  .about-text {
    max-width: 600px;
    text-align: left;
  }
  
  .about-text p {
    font-size: 1rem;
    line-height: 1.6;
    margin-bottom: 20px;
    color: #555;
  }
  
  @media (max-width: 768px) {
    .about-content {
      flex-direction: column;
      text-align: center;
    }
  
    .about-text {
      text-align: center;
    }
  }
  </style>
  