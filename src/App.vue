<template>
    <Navbar/>
    <Schedule/>
    <Gallery/>
    <Story/>
    <!-- <Slide/> -->
  <v-app>

    <v-main>

    </v-main>

  </v-app>

</template>

<script>
import Navbar from './components/Navbar.vue'
import Schedule from './components/Schedule.vue'
import Gallery from './components/Gallery.vue'
import Story from './components/Story.vue'

export default {
  name: 'App',

  components: {
    Navbar,
    Schedule,
    Gallery,
    Story,
  },

  data: () => ({
    //
  }),
}
</script>
