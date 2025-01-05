<script>
import SearchBar from "@/components/SearchBar.vue";
import HeroSection from "@/components/HeroSection.vue";
import AboutSection from "@/components/AboutSection.vue";
import TestimonialSection from "@/components/TestimonialSection.vue";
import CustomMerchSection from "@/components/CustomMerchSection.vue";
import SaleSection from "@/components/SaleSection.vue";
import BestSellerSection from "@/components/BestSellerSection.vue";
import FeaturedProductsSection from "@/components/FeaturedProductsSection.vue";
import FunFactsSection from "@/components/FunFactsSection.vue";
import ContactSection from "@/components/ContactSection.vue";

export default {
  components: {
    SearchBar,
    HeroSection,
    AboutSection,
    TestimonialSection,
    CustomMerchSection,
    SaleSection,
    BestSellerSection,
    FeaturedProductsSection,
    FunFactsSection,
    ContactSection,
  },

  mounted() {
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();

        const targetId = this.getAttribute('href').substring(1);
        const targetElement = document.getElementById(targetId);

        if (targetElement) {
          const headerHeight = document.querySelector('header').offsetHeight;
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
  <div class="page">
    <SearchBar />
    <HeroSection />
    <AboutSection />
    <TestimonialSection/>
    <CustomMerchSection />
    <SaleSection />
    <!-- <BestSellerSection /> -->
    <!-- <FeaturedProductsSection /> -->
    <FunFactsSection />
    <ContactSection />
  </div>
</template>

<style>
section {
  scroll-margin-top: 80px; 
}
</style>