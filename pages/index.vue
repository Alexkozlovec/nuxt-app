<template>
  <section class="homes">
    <ul class="homes__list homes-list">
      <li v-for="home in homes" :key="home.objectID" class="homes-list__item">
        <HomeCard :home="home" />
      </li>
    </ul>
  </section>
</template>

<script>
import homes from '~/data/homes.json'
export default {
  data() {
    return {
      homes: homes.slice(0, 3)
    }
  },
}
</script>

<style scoped>
.homes-list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin: 0;
  padding: 0;
  list-style: none;
}
</style>