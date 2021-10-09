<template>
  <section>
      <h2 class="products__heading">Stay Clean, Feel Clean</h2>
      <div v-if="mobile" class="products__wrapper">
          <div :class="'products__card products__' + card.type" v-for="card in cards.slice(0, 4)" :key="card.id">
              <span class="products__expand">+</span>
              <img :src="'/imgs/' + card.img" class="products__img" :alt="'Product Image for ' + card.name + ' Scented ' + card.type">
              <h3 class="products__title">{{ card.name }}</h3>
          </div>
      </div>
      <div v-else class="products__wrapper">
          <div :class="'products__card products__' + card.type" v-for="card in cards" :key="card.id">
              <span class="products__expand">+</span>
              <img :src="'/imgs/' + card.img" class="products__img" :alt="'Product Image for ' + card.name + ' Scented ' + card.type">
              <h3 class="products__title">{{ card.name }}</h3>
          </div>
      </div>
      <span class="products__soon">*More Scents and Products Coming Soon</span>
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
            ]
        }
    },
}
</script>

<style>

</style>