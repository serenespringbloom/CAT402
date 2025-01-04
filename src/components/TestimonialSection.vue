<script>
export default {
  name: "TestimonialSection",
  data() {
    return {
      testimonials: [
        {
          id: 1,
          name: "Jane Doe",
          text: "Absolutely love the cat mug! It's adorable and high quality.",
          avatar: "https://randomuser.me/api/portraits/women/1.jpg",
        },
        {
          id: 2,
          name: "John Smith",
          text: "The tote bag is perfect for carrying my daily essentials. Highly recommend!",
          avatar: "https://randomuser.me/api/portraits/men/2.jpg",
        },
        {
          id: 3,
          name: "Alice Brown",
          text: "The notebook is my favorite! Such cute and thoughtful designs.",
          avatar: "https://randomuser.me/api/portraits/women/3.jpg",
        },
      ],
    };
  },
};
</script>

<template>
    <section class="testimonials">
      <h2>What Our Customers Say</h2>
      <div class="testimonial-carousel">
        <div
          class="testimonial"
          v-for="testimonial in testimonials"
          :key="testimonial.id"
        >
          <img
            :src="testimonial.avatar"
            :alt="'Avatar of ' + testimonial.name"
            class="testimonial-avatar"
          />
          <p class="testimonial-text">"{{ testimonial.text }}"</p>
          <h4 class="testimonial-name">- {{ testimonial.name }}</h4>
        </div>
      </div>
    </section>
  </template>

<style>
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
    /* Testimonials  */
    .testimonials {
    background-color: #f9f6f2;
    padding: 40px 20px;
    text-align: center;
    }

    .testimonials h2 {
    font-size: 2rem;
    margin-bottom: 20px;
    color: #333;
    }

    .testimonial-carousel {
    justify-content: center;
    display: flex;
    overflow-x: auto;
    gap: 20px;
    padding: 20px;
    scroll-snap-type: x mandatory;
    }

    .testimonial {
    flex: 0 0 300px;
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    padding: 20px;
    text-align: center;
    scroll-snap-align: center;
    transition: transform 0.5s ease, opacity 0.5s ease;
    }

    .testimonial.active {
    transform: translateX(0);
    opacity: 1;
    }
    .testimonial.inactive {
    transform: translateX(-100%);
    opacity: 0;
    }

    .testimonial:hover {
    transform: scale(1.05);
    }

    .testimonial-avatar {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    margin-bottom: 15px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    .testimonial-text {
    font-size: 1rem;
    font-style: italic;
    color: #555;
    margin-bottom: 10px;
    }

    .testimonial-name {
    font-size: 1rem;
    font-weight: bold;
    color: #333;
    }

    /* Responsive Design */
    @media (max-width: 768px) {
    .testimonial-carousel {
        flex-direction: column;
    }

    .testimonial {
        flex: 0 0 auto;
        width: 100%;
    }
    }
</style>