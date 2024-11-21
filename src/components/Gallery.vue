<template>
<div id="gallery"></div>
  <v-container class="gallery">
    <v-row align="center" class="mb-6">
      <v-col cols="12" md="6">
        <h2 class="text-primary font-weight-bold">Photobook</h2>
      </v-col>
      <v-col cols="12" md="6">
        <p>
          A beautiful collection of memories from our special day. Browse through
          and relive the moments that made our wedding unforgettable.
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
export default {
  data() {
    return {
      photos: [
        { src: "photo1.jpg", alt: "Photo 1" },
        { src: "photo2.jpg", alt: "Photo 2" },
        { src: "photo3.jpg", alt: "Photo 3" },
        { src: "photo4.jpg", alt: "Photo 4" },
        { src: "photo5.jpg", alt: "Photo 5" },
        { src: "photo6.jpg", alt: "Photo 6" },
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
  height: 200px;
  object-fit: cover;
}

.gallery-item {
  transition: transform 0.3s ease-in-out;
}

.gallery-item:hover {
  transform: scale(1.05); /* Add a hover effect for interactivity */
}
</style>
