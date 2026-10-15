<script setup>
import { ref } from 'vue'
import CardComp from './components/CardComp.vue'

const movies = ref([
  { title: 'Minecraft', desc: 'Építős-túlélős játék.', rating: 'Értékelés: 9/10' },
  { title: 'Csillagok háborúja', desc: 'Űropera lézerkardokkal.', rating: 'Értékelés: 8/10' },
  { title: 'Tüskevár', desc: 'Kalandok a Sárréten.', rating: 'Értékelés: 10/10' },
  { title: 'Super Mario', desc: 'Ugrálós platformjáték.', rating: 'Értékelés: 9/10' }
])
</script>

<template>
  <div id="app-container">
    <CardComp v-for="(movie, index) in movies" :key="index">
      <template #headerSlot>
        <h3>{{ movie.title }}</h3>
      </template>

      <p>{{ movie.desc }}</p>

      <template #footerSlot>
        {{ movie.rating }}
      </template>
    </CardComp>

    <CardComp>
      <template #headerSlot>
        <h3>Juhász Szabolcs</h3>
      </template>

      <p>Hobbi: kertészkedés és DIY</p>
    </CardComp>
  </div>
</template>

<style>
#app-container {
  display: flex;
  flex-wrap: wrap;
  padding: 20px;
}
h3 {
  margin: 0;
}
p {
  margin: 0;
}
</style>