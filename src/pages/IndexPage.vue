<template>
  <q-page>
    <div class="row">
      <q-card
        flat
        class="card col-sm-12 col-lg-3"
        v-for="(card, index) in cards"
        :key="index"
      >
        <q-img class="card-image" :src="card.image" :alt="card.title" />
        <q-card-section class="q-pt-sm">
          <div class="card-title">{{ card.title }}</div>
          <div class="card-description">{{ card.description }}</div>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from "vue";
defineOptions({
  name: "IndexPage",
});

const cards = ref([
  {
    image: "https://cdn.quasar.dev/img/parallax1.jpg",
    title: "Card 1",
    description: "Description for Card 1",
  },
  {
    image: "https://cdn.quasar.dev/img/parallax2.jpg",
    title: "Card 2",
    description: "Description for Card 2",
  },
  {
    image: "https://cdn.quasar.dev/img/mountains.jpg",
    title: "Card 3",
    description: "Description for Card 3",
  },
  {
    image: "https://cdn.quasar.dev/img/quasar.jpg",
    title: "Card 4",
    description: "Description for Card 4",
  },
  {
    image: "https://cdn.quasar.dev/img/parallax1.jpg",
    title: "Card 1",
    description: "Description for Card 1",
  },
  {
    image: "https://cdn.quasar.dev/img/parallax2.jpg",
    title: "Card 2",
    description: "Description for Card 2",
  },
  {
    image: "https://cdn.quasar.dev/img/mountains.jpg",
    title: "Card 3",
    description: "Description for Card 3",
  },
  {
    image: "https://cdn.quasar.dev/img/quasar.jpg",
    title: "Card 4",
    description: "Description for Card 4",
  },
  {
    image: "https://cdn.quasar.dev/img/parallax1.jpg",
    title: "Card 1",
    description: "Description for Card 1",
  },
  {
    image: "https://cdn.quasar.dev/img/parallax2.jpg",
    title: "Card 2",
    description: "Description for Card 2",
  },
  {
    image: "https://cdn.quasar.dev/img/mountains.jpg",
    title: "Card 3",
    description: "Description for Card 3",
  },
  {
    image: "https://cdn.quasar.dev/img/quasar.jpg",
    title: "Card 4",
    description: "Description for Card 4",
  },
]);
</script>

<style scoped>
@media only screen and (min-device-width: 320px) and (max-device-width: 568px) and (-webkit-device-pixel-ratio: 2) and (orientation: portrait) {
  .card {
    width: 100% !important;
  }
}
.card {
  width: calc(25% - 20px);
  border-radius: 5px;
  height: 300px;
  margin-left: 10px;
  margin-right: 10px;
  margin-bottom: 20px;
}

.card-image {
  max-height: 225px;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}
.card-title {
  font-size: 18px;
  margin-bottom: 5px;
}

.card-description {
  font-size: 14px;
}
</style>
