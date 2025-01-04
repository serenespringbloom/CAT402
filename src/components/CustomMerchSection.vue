<template>
    <section class="custom-merch" id="custom-merch">
      <h2>Create Your Custom Merchandise</h2>
      <p>Choose a product, upload your design, and create personalized merchandise.</p>
  
      <div class="custom-merch-grid">
        <div
          class="custom-merch-card"
          v-for="product in customMerchProducts"
          :key="product.id"
        >
          <img :src="product.image" :alt="product.name" class="custom-merch-image" />
          <h3>{{ product.name }}</h3>
          <p>RM{{ product.price }}</p>
          <button class="select-button" @click="selectProduct(product)">
            Select
          </button>
        </div>
      </div>
  
      <div v-if="selectedProduct" class="custom-merch-form">
        <h3>Customize Your {{ selectedProduct.name }}</h3>
        <div class="merch-preview">
          <img :src="selectedProduct.image" alt="Merchandise" class="merch-image" />
          <img
            v-if="customOrder.previewImage"
            :src="customOrder.previewImage"
            alt="Uploaded Design Preview"
            class="design-preview"
          />
        </div>
        <form @submit.prevent="submitCustomOrder">
          <div class="form-group">
            <label for="customer-name">Your Name</label>
            <input
              v-model="customOrder.name"
              id="customer-name"
              placeholder="Enter your name"
              required
            />
          </div>
          <div class="form-group">
            <label for="customer-email">Your Email</label>
            <input
              type="email"
              v-model="customOrder.email"
              id="customer-email"
              placeholder="Enter your email"
              required
            />
          </div>
          <div class="form-group">
            <label for="design-upload">Upload Your Design</label>
            <input
              type="file"
              id="design-upload"
              @change="handleFileUpload"
              accept="image/*"
              required
            />
          </div>
          <button type="submit" class="submit-button">Submit Order</button>
        </form>
        <p v-if="submissionStatus" class="submission-status">{{ submissionStatus }}</p>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "CustomMerchSection",
    data() {
      return {
        customMerchProducts: [
          {
            id: 1,
            name: "T-Shirt",
            image: "src/assets/images/shirt.jpg",
            price: 50,
          },
          {
            id: 2,
            name: "Mug",
            image: "src/assets/images/mug.jpg",
            price: 30,
          },
          {
            id: 3,
            name: "Tote Bag",
            image: "src/assets/images/tote-bag.jpg",
            price: 40,
          },
          {
            id: 4,
            name: "Cap",
            image: "src/assets/images/cap.jpg",
            price: 35,
          },
        ],
        selectedProduct: null,
        customOrder: {
          name: "",
          email: "",
          file: null,
          previewImage: null,
        },
        submissionStatus: null, // Used to display success or error messages
      };
    },
    methods: {
      selectProduct(product) {
        this.selectedProduct = product;
      },
      handleFileUpload(event) {
        const file = event.target.files[0];
        if (file) {
          this.customOrder.previewImage = URL.createObjectURL(file);
          this.customOrder.file = file;
        }
      },
      submitCustomOrder() {
        if (
          this.customOrder.name &&
          this.customOrder.email &&
          this.customOrder.file
        ) {
          this.submissionStatus = `Thank you! Your custom order for a ${this.selectedProduct.name} has been submitted successfully.`;
          // Reset the form and selection
          this.selectedProduct = null;
          this.customOrder = { name: "", email: "", file: null, previewImage: null };
        } else {
          this.submissionStatus = "Please complete all fields and upload your design.";
        }
      },
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

  .custom-merch {
    padding: 60px 20px;
    background-color: #ffffff;
    background: url("../assets/images/paw-print.png") repeat;
    background-size: 1600px;
    text-align: center;
    color: #333;
  }
  
  .custom-merch h2 {
    font-size: 2.5rem;
    color: #ff6f61;
    margin-bottom: 20px;
  }
  
  .custom-merch p {
    font-size: 1.1rem;
    color: #555;
    margin-bottom: 40px;
  }
  
  .custom-merch-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin-bottom: 40px;
  }
  
  .custom-merch-card {
    background: #ffffff;
    border-radius: 10px;
    padding: 20px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  
  .custom-merch-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 6px 10px rgba(0, 0, 0, 0.15);
  }
  
  .custom-merch-image {
    width: 100%;
    height: 150px;
    object-fit: contain;
    margin-bottom: 10px;
  }
  
  .custom-merch-card h3 {
    font-size: 1.2rem;
    margin-bottom: 10px;
  }
  
  .custom-merch-card p {
    font-size: 1rem;
    font-weight: bold;
    color: #ff6f61;
    margin-bottom: 10px;
  }
  
  .select-button {
    padding: 10px 20px;
    background-color: #ff6f61;
    color: #ffffff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1rem;
    transition: background-color 0.3s ease, transform 0.3s ease;
  }
  
  .select-button:hover {
    background-color: #ec5a50;
    transform: scale(1.05);
  }
  
  .custom-merch-form {
    margin-top: 20px;
    text-align: left;
    background: #ffffff;
    border-radius: 10px;
    padding: 30px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
  }
  
  .custom-merch-form h3 {
    font-size: 1.5rem;
    color: #333;
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
  }
  
  input,
  button {
    width: 100%;
    padding: 15px;
    margin-bottom: 15px;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 1rem;
  }
  
  input:focus {
    border-color: #ff6f61;
    box-shadow: 0 4px 8px rgba(255, 111, 97, 0.2);
    outline: none;
  }
  
  .submit-button {
    background-color: #ff6f61;
    color: #ffffff;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.3s ease;
  }
  
  .submit-button:hover {
    background-color: #ec5a50;
    transform: scale(1.05);
  }
  
  .submission-status {
    margin-top: 15px;
    font-size: 1rem;
    color: #333;
  }
  
  .merch-preview {
    position: relative;
    width: 300px;
    height: 300px;
    margin: 20px auto;
  }
  
  .merch-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
  }
  
  .design-preview {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    max-width: 80%;
    max-height: 80%;
    opacity: 0.8;
    border: 2px dashed #ff6f61;
    pointer-events: none;
  }
  
  @media (max-width: 768px) {
    .custom-merch-grid {
      grid-template-columns: 1fr;
    }
  
    .custom-merch-form {
      padding: 20px;
    }
  }
  </style>
  