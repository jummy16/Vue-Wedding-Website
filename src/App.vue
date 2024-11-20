<template>
    <Navbar/>
    <Schedule/>
    <!-- <Slide/> -->
  <v-app>

    <v-main>

    </v-main>

  </v-app>

</template>

<script>
import Navbar from './components/Navbar.vue'
import Schedule from './components/Schedule.vue'
// import Slide from './components/Slide.vue'

export default {
  name: 'App',

  components: {
    Navbar,
    Schedule,
    // Slide,
  },

  data: () => ({
    //
  }),
}
</script>
