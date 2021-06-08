<template>
  <Header/>
  <Sommeliers/>
  <Features/>
  <Story/>
  <Wines/>
  <Gallery/>
</template>

<script>
import Header from '@/views/home/Header.vue'
import Sommeliers from '@/views/home/Sommeliers.vue'
import Features from '@/views/home/Features.vue'
import Story from '@/views/home/Story.vue'
import Wines from '@/views/home/Wines.vue'
import Gallery from '@/views/home/Gallery.vue'

export default {
  name: 'Home',
  components: {
    Header,
    Sommeliers,
    Features,
    Story,
    Wines,
    Gallery,
  }
}
</script>
