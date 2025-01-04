<template>
    <section class="best-sellers">
      <h2>Best Sellers</h2>
      <div class="best-sellers-carousel">
        <div class="best-seller-card" v-for="product in bestSellers" :key="product.id">
          <img :src="product.image" :alt="product.name" class="best-seller-image" />
          <h3>{{ product.name }}</h3>
          <p class="best-seller-price">RM{{ product.price }}</p>
          <button class="shop-now-button">Shop Now</button>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "BestSellerSection",
    data() {
      return {
      bestSellers: [
        {
          id: 1,
          name: 'Cat Scratching Post',
          image: 'src/assets/images/cat-post.jpg',
          price: 120,
        },
        {
          id: 2,
          name: 'Cat Bed',
          image: 'src/assets/images/cat-bed.jpg',
          price: 90,
        },
        {
          id: 3,
          name: 'Cat Tower',
          image: 'src/assets/images/cat-tower.jpg',
          price: 300,
        },
        {
          id: 4,
          name: 'Cat Brush',
          image: 'src/assets/images/cat-brush.jpg',
          price: 25,
        },
        {
          id: 5,
          name: 'Cat Blanket',
          image: 'src/assets/images/cat-blanket.jpg',
          price: 50,
        },
        {
          id: 6,
          name: 'Cat Food Bowl',
          image: 'src/assets/images/cat-food-bowl.jpg',
          price: 40,
        },
        {
          id: 7,
          name: 'Cat Toy Mouse',
          image: 'src/assets/images/cat-mouse.jpg',
          price: 15,
        },
        {
          id: 8,
          name: 'Cat Collar with Bell',
          image: 'src/assets/images/cat-collar.jpg',
          price: 20,
        },
        {
          id: 9,
          name: 'Cat Hammock',
          image: 'src/assets/images/cat-hammock.jpg',
          price: 100,
        },
        {
          id: 10,
          name: 'Cat Litter Box',
          image: 'src/assets/images/cat-litter.jpg',
          price: 120,
        },
      ],
      };
    },
  };
  </script>
  
<style scoped>

/* Best Sellers Section */
.best-sellers {
  padding: 40px 20px;
  background-color: #f9f6f2;
  text-align: center;
}

.best-sellers h2 {
  font-size: 2rem;
  margin-bottom: 20px;
  color: #333;
}

.best-sellers-carousel {
  display: flex;
  overflow-x: auto;
  gap: 20px;
  padding: 20px;
  scroll-snap-type: x mandatory;
  scrollbar-width: thin; /* For Firefox */
  scrollbar-color: #ff6f61 #f9f6f2;
}

.best-seller-card {
  flex: 0 0 auto;
  width: 200px;
  background-color: #fff;
  border-radius: 10px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  scroll-snap-align: center;
}

.best-seller-card:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
}

.best-seller-image {
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 15px;
}

.best-seller-card h3 {
  font-size: 1.2rem;
  color: #333;
  margin-bottom: 10px;
}

.best-seller-price {
  font-size: 1.2rem;
  font-weight: bold;
  color: #ff6f61;
  margin-bottom: 15px;
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

/* Scrollbar Styling */
.best-sellers-carousel::-webkit-scrollbar {
  height: 8px;
}

.best-sellers-carousel::-webkit-scrollbar-thumb {
  background-color: #ff6f61;
  border-radius: 5px;
}

.best-sellers-carousel::-webkit-scrollbar-track {
  background-color: #f9f6f2;
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  .best-seller-card {
    width: 150px;
  }

  .best-seller-image {
    height: 120px;
  }

  .best-seller-card h3 {
    font-size: 1rem;
  }

  .best-seller-price {
    font-size: 1rem;
  }

  .shop-now-button {
    font-size: 0.9rem;
    padding: 8px 16px;
  }
}
</style>
  