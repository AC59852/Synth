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
  <Hero id="hero" class="hero"/>
  <Products id="products" class="products"/>
  <About id="about" class="about"/>
  <Contact id="contact" class="contact"/>
</template>
