<template>
    
  <v-app>

    <v-main>
      <Navbar/>
    <Schedule/>
    <Gallery/>
    <Story/>
    <Message/>
    <Vendor/>
    </v-main>

  </v-app>

</template>

<script>
import Navbar from './components/Navbar.vue'
import Schedule from './components/Schedule.vue'
import Gallery from './components/Gallery.vue'
import Story from './components/Story.vue'
import Message from './components/Message.vue'
import Vendor from './components/Vendor.vue'

export default {
  name: 'App',

  components: {
    Navbar,
    Schedule,
    Gallery,
    Story,
    Message,
    Vendor,
  },

  data: () => ({
    //
  }),
}
</script>

<style>
 

</style>
