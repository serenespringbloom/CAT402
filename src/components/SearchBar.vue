<template>
    <div class="search-bar" id="search-bar">
      <input
        type="text"
        v-model="searchQuery"
        placeholder="Search for products..."
        aria-label="Search for products"
        @keyup.enter="onSearch"
      />
      <button class="search-button" aria-label="Search" @click="onSearch">
        <i class="fa fa-search"></i> <!-- Font Awesome Icon -->
      </button>
    </div>
  </template>
  
  <script>
  export default {
    name: "SearchBar",
    data() {
      return {
        searchQuery: "", // Stores the user's search input
      };
    },
    methods: {
      onSearch() {
        if (this.searchQuery.trim() !== "") {
          console.log("Search query:", this.searchQuery); // Replace with actual search logic
          // Emit the search query to parent component or handle the search
          this.$emit("search", this.searchQuery);
        } else {
          alert("Please enter a search term.");
        }
      },
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

/* Search Bar */
.search-bar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 20px auto;
  padding: 10px;
  max-width: 600px;
  background-color: #ffffff !important; /* Force white background */
  background-image: url('../assets/images/paw-print.png');
  background-size: 500px;
  background-repeat: no-repeat;
  border-radius: 30px; /* Smooth rounded edges */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); /* Soft shadow */
  transition: box-shadow 0.3s ease, transform 0.3s ease;
}

.search-bar:hover {
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.15);
  transform: scale(1.02);
}

.search-bar input {
  flex: 1;
  padding: 15px 20px;
  border: none;
  border-radius: 30px 0 0 30px; /* Rounded edge only on the left */
  font-size: 1rem;
  background-color: #f9f9f9; /* Neutral background */
  color: #333; /* Text color */
  outline: none;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.search-bar input:focus {
  background-color: #fff; /* Ensure focus remains visible */
  box-shadow: 0 0 5px rgba(255, 111, 97, 0.5);
}

.search-bar button {
  padding: 10px 30px;
  border: none;
  border-radius: 0 30px 30px 0; /* Rounded edge only on the right */
  background: linear-gradient(135deg, #ff6f61, #ff8a76); /* Gradient button */
  color: #fff;
  font-size: 1.2rem;
  font-weight: bold;
  cursor: pointer;
  transition: background 0.3s ease, transform 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 30%;
}

.search-bar button:hover {
  background: linear-gradient(135deg, #ec5a50, #ff7268);
  transform: scale(1.05);
}

.search-bar button i {
  font-size: 1.5rem; /* Larger icon size */
}

@media (max-width: 768px) {
  .search-bar {
    flex-direction: column;
    max-width: 90%;
    padding: 15px;
  }

  .search-bar input,
  .search-bar button {
    width: 100%;
    border-radius: 30px; /* Uniform rounded edges for mobile */
    margin-bottom: 10px;
  }
}
  </style>
  