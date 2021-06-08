<template>
<div class="container">
  <Sidebar/>
  <router-view/>
</div>
  <Footer/>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue'
import Footer from '@/views/Footer.vue'

export default {
  components: {
    Sidebar,
    Footer,
  },
  setup() {
    
  },
}
</script>