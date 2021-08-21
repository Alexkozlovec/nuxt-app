<template>
  <div class="home-card">
    <img class="home-card__image" :src="home.images[0]" width="200" />
    <h3 class="home-card__title">
      {{ home.title }}
    </h3>
    <p class="home-card__location">
      {{ home.location.address }} {{ home.location.city }} {{ home.location.state }}
    </p>
    <p class="home-card__guests">
      {{ home.guests }}
    </p>
    <p class="home-card__price">
      {{ home.pricePerNight }} / night
    </p>
  </div>
</template>

<script>
export default {
  props: {
    home: {
      type: Object,
      required: true
    },
  },
}
</script>

<style scoped></style>