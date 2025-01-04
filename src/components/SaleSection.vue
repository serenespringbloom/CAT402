<template>
    <section class="sale">
      <div class="sale-banner">
        <h2>🔥 Limited-Time Sale! 🔥</h2>
        <p>Up to 50% Off on Selected Items!</p>
        <div id="countdown" class="countdown-timer">{{ countdown }}</div>
      </div>
  
      <div class="sale-products">
        <div class="product" v-for="product in saleProducts" :key="product.id">
          <img :src="product.image" :alt="product.name" />
          <h3>{{ product.name }}</h3>
          <p class="original-price">RM{{ product.originalPrice }}</p>
          <p class="discounted-price">RM{{ product.discountedPrice }}</p>
          <button class="shop-now-button">Shop Now</button>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "SaleSection",
    data() {
      return {
        saleProducts: [
          {
            id: 1,
            name: "Cat Hoodie",
            image: "src/assets/images/cat-hoodie.jpg",
            originalPrice: 100,
            discountedPrice: 50,
          },
          {
            id: 2,
            name: "Cat Bowl",
            image: "src/assets/images/cat-bowl.jpg",
            originalPrice: 80,
            discountedPrice: 40,
          },
          {
            id: 3,
            name: "Cat Pillow",
            image: "src/assets/images/cat-pillow.jpg",
            originalPrice: 60,
            discountedPrice: 30,
          },
        ],
        countdown: "",
      };
    },
    methods: {
      updateCountdown() {
        const targetDate = new Date("2025-12-31T23:59:59").getTime();
        const now = new Date().getTime();
        const distance = targetDate - now;
  
        if (distance > 0) {
          const days = Math.floor(distance / (1000 * 60 * 60 * 24));
          const hours = Math.floor(
            (distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
          );
          const minutes = Math.floor(
            (distance % (1000 * 60 * 60)) / (1000 * 60)
          );
          const seconds = Math.floor((distance % (1000 * 60)) / 1000);
  
          this.countdown = `${days}d ${hours}h ${minutes}m ${seconds}s`;
        } else {
          this.countdown = "SALE ENDED";
        }
      },
    },
    mounted() {
      this.updateCountdown();
      setInterval(this.updateCountdown, 1000);
    },
  };
  </script>
  
<style scoped>
html {
  scroll-behavior: smooth;
}

section {
  scroll-margin-top: 80px; /* Adjust to match the header height */
}

/* General Styles */

button:hover {
  box-shadow: 0 8px 15px rgba(255, 111, 97, 0.4);
  transform: translateY(-3px);
}

h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  color: #333;
  text-align: center;
}

p, li {
  font-size: 1rem;
  line-height: 1.5;
  color: #555;
}

ul {
  list-style: none;
  padding: 0;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.section {
  opacity: 0;
  animation: fadeIn 1s ease-in forwards;
}

/* Sale Section */
.sale {
  padding: 40px 20px;
  background: linear-gradient(135deg, #ffecd2, #fcb69f);
  text-align: center;
}

.sale-banner {
  margin-bottom: 30px;
  background-color: #ff6f61;
  color: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.sale-banner h2 {
  font-size: 2rem;
  margin: 0 0 10px;
}

.sale-banner p {
  font-size: 1.2rem;
  margin: 0 0 20px;
}

.countdown-timer {
  font-size: 1.5rem;
  font-weight: bold;
  color: #fff;
  background: rgba(0, 0, 0, 0.3);
  padding: 10px 20px;
  border-radius: 5px;
  display: inline-block;
}

.sale-products {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin-top: 30px;
}

.product {
  background-color: #fff;
  border-radius: 10px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.product:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
}

.product img {
  width: 100%;
  max-width: 180px; /* Adjust max-width for the desired image size */
  height: 180px; /* Fixed height for uniformity */
  object-fit: cover; /* Ensures the image maintains its aspect ratio */
  border-radius: 8px;
  margin-bottom: 10px;
}

.product h3 {
  font-size: 1.2rem;
  margin: 10px 0;
}

.original-price {
  text-decoration: line-through;
  color: #888;
  margin: 5px 0;
}

.discounted-price {
  color: #ff6f61;
  font-size: 1.5rem;
  font-weight: bold;
}

.shop-now-button {
  margin-top: 10px;
  padding: 10px 20px;
  background-color: #ff6f61;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.shop-now-button:hover {
  background-color: #ec5a50;
}
</style>
  