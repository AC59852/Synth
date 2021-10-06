<template>
  <header class="header">
      <nav class="header__bar">
          <a href="#" class="header__title"><h1>Synth</h1></a>
          <img src="../assets/nav_btn.svg" @click="playNavAnim()" alt="Navigation Menu Icon" class="header__btn">
              <ul class="header__navigation">
                  <span @click="removeNavAnim()" class="header__close">X</span>
                  <li @click="removeNavAnim()" class="header__item"><a v-scroll-to="'#home'" class="header__link" href="#">Home</a></li>
                  <li @click="removeNavAnim()" class="header__item"><a class="header__link" href="#">Products</a></li>
                  <li @click="removeNavAnim()" class="header__item"><a class="header__link" href="#">About</a></li>
                  <li @click="removeNavAnim()" class="header__item"><a class="header__link" href="#">Contact</a></li>
              </ul>
      </nav>
  </header>
</template>

<script>
export default {
    methods: {
        playNavAnim() {
            let nav = document.querySelector(".header__navigation"),
                navItem = document.querySelectorAll(".header__link");

            nav.classList.add("revealNav");
            navItem.forEach(item => { item.classList.add("revealItem") })
        },

        removeNavAnim() {
           let nav = document.querySelector(".header__navigation"),
               navItem = document.querySelectorAll(".header__link");

            nav.classList.remove("revealNav");
            navItem.forEach(item => { item.classList.remove("revealItem") }) 
        }
    }
}
</script>

<style>

</style>