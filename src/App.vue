<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import Navigation from "./components/Navigation.vue";
import Hero from "./components/Hero.vue";
import Products from "./components/Products.vue";
import About from "./components/About.vue";
import Contact from "./components/Contact.vue";
</script>

<template>
  <Navigation />
  <Hero id="hero" class="hero wrapper"/>
  <Products id="products" class="products wrapper"/>
  <About id="about" class="about wrapper"/>
  <Contact id="contact" class="contact wrapper"/>
</template>
