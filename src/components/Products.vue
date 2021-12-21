<template>
  <section>
      <transition name="fade">
      <div class="popup" v-show="popupToggled">
          <div class="popup__wrapper">
              <span class="popup__close" @click="hidePopup()">X</span>
              <div class="popup__imageWrapper">
                  <img id="popup__image" class="popup__image" src="/" alt="">
                  <h2 class="popup__title popup__title--mobile" v-if="mobile">{{ currentCard.name }}</h2>
              </div>
              <div class="popup__text">
                  <h2 class="popup__title popup__title--desktop" v-if="tablet || desktop">{{ currentCard.name }}</h2>
                  <p class="popup__para" v-for="para in currentCard.desc" :key="para.id">{{ para.content }}</p>
              </div>
          </div>
      </div>
      </transition>
      <h2 v-if="mobile" class="products__heading">Stay Clean, Feel Clean</h2>
      <div v-else class="products__textWrapper">
        <h2 class="products__heading products__heading--desktop">Enjoy Life Without Worries. Stay Clean, Feel Clean.</h2>
        <span class="products__soon">*More Scents and Products Coming Soon</span>
      </div>
      <div class="products__wrapper">
          <div :class="'products__card products__' + card.type" v-for="card in cards.slice(0, 4)" :key="card.id" @click="showPopup(card)">
              <span class="products__expand">+</span>
              <img :src="'/imgs/' + card.img" class="products__img" :alt="'Product Image for ' + card.name + ' Scented ' + card.type">
              <h3 class="products__title">{{ card.name }}</h3>
          </div>
      </div>
      <span v-if="mobile" class="products__soon">*More Scents and Products Coming Soon</span>
  </section>
</template>

<script>
export default {
    data() {
        return {
            mobile: true,
            tablet: false,
            desktop: false,
            popupToggled: false,

            currentCard: {},
            
            cards: [
                {id: 0, name: 'Lemon Grass', type: 'Hand Sanitizer', img: 'bottle.png', expandedImg: 'about_placeholder1.jpg', desc: [
                    {id: 1, content: 'Aliquet aliquam ultrices nunc urna nam nibh. Auctor posuere ut ipsum at justo. Nulla ornare sit consectetur tortor morbi lobortis. Fermentum faucibus quam elit viverra volutpat eros, vitae viverra phasellus. Sit vitae lobortis erat sollicitudin. Vestibulum dignissim sed elit sed cras augue nulla. Ipsum, lectus eget varius mi, est turpis viverra. Ut sem nulla urna, nunc sit a viverra eu. Laoreet luctus varius eget feugiat in. Suscipit.'},
                    {id: 2, content: 'Sit ultrices venenatis lacinia eget neque. Pulvinar sit odio fringilla convallis. Morbi urna porttitor tempus, odio lacus pellentesque gravida lacinia euismod. Convallis feugiat consectetur posuere sed feugiat viverra lorem.'},
                ]},
            ]
        }
    },

    mounted() {
        this.checkScreenSize();
        window.addEventListener('resize', this.checkScreenSize);
    },

    methods: {
        checkScreenSize() {
            if (window.innerWidth < 768) {
                this.mobile = true;
                this.tablet = false;
                this.desktop = false;
            } else if (window.innerWidth >= 768) {
                this.mobile = false;
                this.tablet = true;
                this.desktop = false;
            } else if (window.innerWidth >= 1080) {
                this.mobile = false;
                this.tablet = false;
                this.desktop = true;
            }
        },

        showPopup(card) {
            this.currentCard = card;
            this.popupToggled = !this.popupToggled;
            console.log(this.currentCard)

            const imgUrl = new URL('../../public/imgs/' + card.expandedImg, import.meta.url)
            document.getElementById('popup__image').src = imgUrl

            // prevent body from scrolling
            document.body.style.overflow = 'hidden';
        },

        hidePopup() {
            this.popupToggled = !this.popupToggled;
            document.body.style.overflow = 'auto';
        }
    }
}
</script>

<style>

</style>