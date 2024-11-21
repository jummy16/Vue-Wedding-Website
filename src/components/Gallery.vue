<template>
<div id="gallery"></div>
  <v-container class="gallery">
    <v-row align="center" class="mb-6">
      <v-col cols="12" md="6">
        <h2 class="text-primary font-weight-bold">Photobook</h2>
      </v-col>
      <v-col cols="12" md="6">
        <p>
          Captured moments of love and joy—our journey to forever begins here.
        </p>
      </v-col>
    </v-row>

    <!-- Photo Gallery -->
    <v-row class="gallery-grid">
      <v-col
        cols="12"
        sm="6"
        md="4"
        lg="3"
        v-for="(photo, index) in photos"
        :key="index"
        class="gallery-item"
      >
        <v-card>
          <v-img :src="photo.src" :alt="photo.alt" class="gallery-img" />
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>


<script>
import Photo1 from '../assets/omo(18).jpg'
import Photo2 from '../assets/omo(19).jpg'
import Photo3 from '../assets/omo(25).jpg'
import Photo4 from '../assets/omo(16).jpg'
import Photo5 from '../assets/omo(26).jpg'
import Photo6 from '../assets/omo(32).jpg'
export default {
  data() {
    return {
      photos: [

        { src: Photo1, alt: "Photo 1" },
        { src: Photo2, alt: "Photo 2" },
        { src: Photo3, alt: "Photo 3" },
        { src: Photo4, alt: "Photo 4" },
        { src: Photo5, alt: "Photo 5" },
        { src: Photo6, alt: "Photo 6" },
      ],
    };
  },
};
</script>


<style scoped>
.gallery{
    background-color: #E6CCE6;
    max-width: 100%;
}
.text-primary {
  color: #ff6f61; 
}

.gallery-grid {
  gap: 16px; 
  justify-content: center;
}

.gallery-img {
  object-fit: cover;
}

.gallery-item {
  transition: transform 0.3s ease-in-out;
}

.gallery-item:hover {
  transform: scale(1.05); 
  transition: 1s;
}
</style>
