<template>
    
  <v-app>
    <v-app-bar app >
      <v-toolbar-title>
        <img src="../assets/JT wedding logo.webp" alt="Wedding Logo" height="50">
      </v-toolbar-title>
      
      <v-spacer></v-spacer>
      
      <v-btn text>THE COUPLE</v-btn>
      <v-btn text>EVENT SCHEDULE</v-btn>
      <v-btn text>GALLERY</v-btn>
      <v-btn text>COUPLE STORY</v-btn>
      <v-btn text>MESSAGE</v-btn>
      <v-btn text>VENDORS</v-btn>
    </v-app-bar>

    
    <v-main>
        <div class="main-content">
          <div class="overlay-content">
            <h1>Step into heaven on earth, a place where God's love thrives and victory is assured</h1>
            <p>Join us on our special day</p>
            <p>#JT25</p>
            <v-btn class="rsvp" @click="showRSVP= true">RSVP</v-btn>
          </div>
        </div>
    </v-main>

    <v-dialog v-model="showRSVP" max-width='500'>
      <v-card>
        <v-card-title>You're Invited!</v-card-title>
        <img src="" alt="">
      </v-card>
    </v-dialog>
  </v-app>
</template>

<script>
export default {
  components: { },
  name: 'Navbar',
};

</script>

<style scoped>
.main-content{
  height: 100vh; 
  background-image: url('../assets/omo(23).jpg'); 
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: white;
}
.overlay-content {
  background-color: rgba(0, 0, 0, 0.5); 
  padding: 20px;
  border-radius: 10px;
}
.rsvp{
  color: black;
}
</style>
