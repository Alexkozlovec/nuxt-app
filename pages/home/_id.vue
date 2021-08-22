<template>
  <div>
    <div style="display: flex;">
      <img 
        v-for="image in home.images" 
        :key="image" 
        :src="image" 
        :alt="home.title" 
        width="200" 
        height="150"
      >
    </div>
    <h3>{{ home.title }}</h3>
    <p>${{ home.pricePerNight }} / night</p>
    <p>
      <img src="/images/marker.svg" alt="location marker" width="20" height="20">
      <span>{{ home.location.address }} {{ home.location.city }} {{ home.location.state }} {{ home.location.country }}</span>
    </p>
    <p>
      <img src="/images/star.svg" alt="star" width="20" height="20" />
      <span>{{ home.reviewValue }}</span>
    </p>
    <ul>
      <li>{{ home.guests }} guests</li>
      <li>{{ home.bedrooms }} rooms</li>
      <li>{{ home.beds }} beds</li>
      <li>{{ home.bathrooms }} bath</li>
    </ul>
  </div>
</template>

<script>
import homes from '~/data/homes'

export default {
  head() {
    return {
      title: this.home.title
    }
  },
  data() {
    return {
      home: {}
    }
  },
  created() {
    const home = homes.find(h => h.objectID === this.$route.params.id)
    this.home = home
  }
}
</script>