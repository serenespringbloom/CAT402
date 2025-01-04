<template>
    <section class="featured-products">
      <h2>Our Featured Products</h2>
      <div class="featured-product-grid">
        <div class="featured-product-card" v-for="product in featuredProducts" :key="product.id">
          <img :src="product.image" :alt="product.name" class="featured-product-image" />
          <div class="featured-product-info">
            <h3 class="featured-product-name">{{ product.name }}</h3>
            <p class="featured-product-description">{{ product.description }}</p>
            <p class="featured-product-price">RM{{ product.price }}</p>
            <button class="shop-now-button">Shop Now</button>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "FeaturedProductsSection",
    data() {
      return {
        featuredProducts: [
          {
            id: 1,
            name: "Luxury Cat Bed",
            description: "A cozy and stylish bed for your feline friend.",
            image: "src/assets/images/cat-luxury.jpg",
            price: 150,
          },
          {
            id: 2,
            name: "Interactive Cat Toy",
            description: "Keep your cat entertained for hours with this toy.",
            image: "src/assets/images/cat-toy.jpg",
            price: 60,
          },
          {
            id: 3,
            name: "Automatic Cat Feeder",
            description: "Ensure your cat is always fed with this smart feeder.",
            image: "src/assets/images/cat-feeder.jpg",
            price: 300,
          },
          {
            id: 4,
            name: "Cat Water Fountain",
            description: "Provide fresh water for your cat all day long.",
            image: "src/assets/images/cat-water.jpg",
            price: 120,
          },
          {
            id: 5,
            name: "Cat Harness & Leash",
            description: "Take your cat on safe and stylish outdoor adventures.",
            image: "src/assets/images/cat-harness.jpg",
            price: 80,
          },
          {
            id: 6,
            name: "Cat Grooming Kit",
            description: "Everything you need to keep your cat looking its best.",
            image: "src/assets/images/cat-kit.jpg",
            price: 90,
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
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

button {
  width: 100%;
  padding: 15px;
  margin-bottom: 15px;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 1rem;
}

.featured-products {
  padding: 60px 20px;
  background-color: #f9f6f2;
  text-align: center;
}

.featured-products h2 {
  font-size: 2rem;
  margin-bottom: 30px;
  color: #333;
}

.featured-product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}

.featured-product-card {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.featured-product-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
}

.featured-product-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.featured-product-info {
  padding: 20px;
  text-align: left;
}

.featured-product-name {
  font-size: 1.2rem;
  margin-bottom: 10px;
  color: #333;
}

.featured-product-description {
  font-size: 0.9rem;
  margin-bottom: 10px;
  color: #555;
}

.featured-product-price {
  font-size: 1.2rem;
  color: #ff6f61;
  font-weight: bold;
  margin-bottom: 10px;
}

.shop-now-button {
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
  
  /* Responsive Design */
  @media (max-width: 768px) {
    .featured-product-image {
      height: 150px;
    }
  
    .featured-product-name {
      font-size: 1rem;
    }
  
    .featured-product-description {
      font-size: 0.8rem;
    }
  
    .featured-product-price {
      font-size: 1rem;
    }
  
    .shop-now-button {
      font-size: 0.9rem;
      padding: 8px 16px;
    }
  }
  </style>
  