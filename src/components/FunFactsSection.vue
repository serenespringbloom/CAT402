<template>
    <section class="fun-facts">
      <h2>Fun Facts About Cats</h2>
      <div class="fun-facts-grid">
        <div class="fun-fact-card" v-for="fact in funFacts" :key="fact.id">
          <img :src="fact.image" :alt="fact.fact" class="fun-fact-image" />
          <p class="fun-fact-text">{{ fact.fact }}</p>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "FunFactsSection",
    data() {
      return {
        funFacts: [
          {
            id: 1,
            fact: "Cats sleep 70% of their lives.",
            image: "src/assets/images/sleeping-cat.jpg",
          },
          {
            id: 2,
            fact: "The oldest cat lived to be 38 years old.",
            image: "src/assets/images/oldest-cat.jpg",
          },
          {
            id: 3,
            fact: "Cats can make over 100 different sounds.",
            image: "src/assets/images/sound-cat.jpg",
          },
          {
            id: 4,
            fact: "A group of cats is called a clowder.",
            image: "src/assets/images/group-cat.jpg",
          },
          {
            id: 5,
            fact: "Cats can run up to 30 miles per hour.",
            image: "src/assets/images/running-cat.jpg",
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
  .fun-facts {
    padding: 60px 20px;
    background-color: #f3f3f3;
    text-align: center;
  }
  
  .fun-facts h2 {
    font-size: 2rem;
    margin-bottom: 30px;
    color: #333;
  }
  
  .fun-facts-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
    justify-content: center;
  }
  
  .fun-fact-card {
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    text-align: center;
  }
  
  .fun-fact-card:hover {
    transform: scale(1.05);
    box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
  }
  
  .fun-fact-image {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-bottom: 2px solid #ff6f61;
  }
  
  .fun-fact-text {
    padding: 15px;
    font-size: 1rem;
    line-height: 1.5;
    color: #555;
  }
  
  /* Responsive Design */
  @media (max-width: 768px) {
    .fun-fact-image {
      height: 120px;
    }
  
    .fun-fact-text {
      font-size: 0.9rem;
    }
  }
  </style>
  