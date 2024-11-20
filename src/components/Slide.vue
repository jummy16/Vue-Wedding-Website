<template>
  <v-container>
    <v-carousel :cycle="true" :interval="5000" show-arrows-on-hover>
      <v-carousel-item v-for="(image, index) in images" :key="index">
        <v-img :src="image" height="500px"></v-img>
      </v-carousel-item>
    </v-carousel>
  </v-container>
</template>

<script>
export default {
  name: 'Slide',
  data() {
    return {
      images: [
        '../assets/omo(107).jpg',
        '../assets/omo(23).jpg',
        '../assets/omo(25).jpg', 
      ],
    };
  },
};
</script>

<style scoped>

</style>
