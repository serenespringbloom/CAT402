<template>
    <section class="contact">
      <h2>Contact Us</h2>
      <p class="contact-description">
        Have questions, feedback, or need assistance? We’d love to hear from you!
      </p>
      <form @submit.prevent="submitForm" class="contact-form">
        <div class="form-group">
          <input
            type="text"
            v-model="contactForm.name"
            placeholder="Your Name"
            required
            aria-label="Your Name"
          />
        </div>
        <div class="form-group">
          <input
            type="email"
            v-model="contactForm.email"
            placeholder="Your Email"
            required
            aria-label="Your Email"
          />
        </div>
        <div class="form-group">
          <textarea
            v-model="contactForm.message"
            placeholder="Your Message"
            required
            aria-label="Your Message"
          ></textarea>
        </div>
        <button type="submit" class="submit-button">Send Message</button>
        <p v-if="submissionStatus" class="submission-status">
          {{ submissionStatus }}
        </p>
      </form>
      <div class="contact-details">
        <h3>Reach Us At:</h3>
        <p>
          <strong>Email:</strong> support@meowchandise.my
        </p>
        <p>
          <strong>Phone:</strong> +6012-345-6789
        </p>
        <p>
          <strong>Address:</strong> 123 Meow Street, Cat City, Malaysia
        </p>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        contactForm: {
          name: "",
          email: "",
          message: "",
        },
        submissionStatus: null, // Success or error message
      };
    },
    methods: {
      submitForm() {
        if (this.contactForm.name && this.contactForm.email && this.contactForm.message) {
          this.submissionStatus = "Thank you! Your message has been sent successfully.";
          this.contactForm = { name: "", email: "", message: "" };
        } else {
          this.submissionStatus = "Please fill in all fields.";
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .contact {
    padding: 60px 20px;
    background: linear-gradient(to right, #f9f6f2, #f3c677);
    text-align: center;
    color: #333;
    border-radius: 10px;
  }
  
  .contact h2 {
    font-size: 2.5rem;
    margin-bottom: 20px;
    color: #ff6f61;
  }
  
  .contact-description {
    font-size: 1.2rem;
    margin-bottom: 30px;
    line-height: 1.6;
    color: #555;
  }
  
  .contact-form {
    margin: 0 auto 40px;
    max-width: 600px;
    background: #fff;
    border-radius: 10px;
    padding: 30px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  input,
  textarea {
    width: 100%;
    padding: 15px;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 1rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: border-color 0.3s ease, box-shadow 0.3s ease;
  }
  
  input:focus,
  textarea:focus {
    border-color: #ff6f61;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
    outline: none;
  }
  
  textarea {
    min-height: 120px;
    resize: none;
  }
  
  .submit-button {
    width: 100%;
    padding: 15px;
    background-color: #ff6f61;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1.2rem;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.2s ease;
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
  
  .contact-details {
    text-align: left;
    max-width: 600px;
    margin: 0 auto;
    font-size: 1.1rem;
    line-height: 1.8;
    color: #333;
  }
  
  .contact-details h3 {
    font-size: 1.5rem;
    margin-bottom: 15px;
    color: #ff6f61;
  }
  
  .contact-details p strong {
    color: #ff6f61;
  }
  
  @media (max-width: 768px) {
    .contact-form {
      padding: 20px;
    }
  }
  </style>
  