<template>
  <section>
      <h2>Stay Clean, Feel Clean</h2>
      <div v-if="mobile" class="products__wrapper">
          <div :class="'products__card products__' + card.type" v-for="card in cards.slice(0, 3)" :key="card.id">
              <span class="products__expand">+</span>
              <img :src="'/imgs/' + card.img" class="products__img" :alt="'Product Image for ' + card.name + ' Scented ' + card.type">
              <h3 class="products__title">{{ card.name }}</h3>
          </div>
      </div>
      <div v-else class="products__wrapper">
          <div :class="'products__card products__' + card.type" v-for="card in cards.slice(0, 3)" :key="card.id">
              <span class="products__expand">+</span>
              <img :src="'/imgs/' + card.img" class="products__img" :alt="'Product Image for ' + card.name + ' Scented ' + card.type">
              <h3 class="products__title">{{ card.name }}</h3>
          </div>
      </div>
  </section>
</template>

<script>
export default {
    data() {
        return {
            mobile: true,

            currentCard: {},
            
            cards: [
                {id: 0, name: 'Lemon Grass', type: 'Hand Sanitizer', img: 'bottle.png'},
                {id: 1, name: 'Vanilla', type: 'Hand Sanitizer', img: 'bottle.png'},
                {id: 2, name: 'Eucalyptus', type: 'Hand Sanitizer', img: 'bottle.png'},
                {id: 3, name: 'Lavender', type: 'Hand Sanitizer', img: 'bottle.png'},
                {id: 4, name: 'Cinnamon', type: 'Hand Sanitizer', img: 'bottle.png'},
                {id: 5, name: 'Pine', type: 'Hand Sanitizer', img: 'bottle.png'},
            ]
        }
    },
}
</script>

<style>

</style>