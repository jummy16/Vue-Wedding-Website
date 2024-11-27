<template>
  <v-app>
    <v-app-bar>
      <v-toolbar-title>
        <img src="../assets/JT wedding logo.webp" alt="Wedding Logo" height="50" />
      </v-toolbar-title>

      <!-- Desktop Navigation Buttons -->
      <v-spacer class="d-none d-md-flex"></v-spacer>
      <v-btn class="d-none d-md-flex" text href="#The couple">THE COUPLE</v-btn>
      <v-btn class="d-none d-md-flex" text href="#schedule">EVENT SCHEDULE</v-btn>
      <v-btn class="d-none d-md-flex" text href="#gallery">GALLERY</v-btn>
      <v-btn class="d-none d-md-flex" text href="#couple-story">COUPLE STORY</v-btn>
      <v-btn class="d-none d-md-flex" text href="#message">MESSAGE</v-btn>
      <v-btn class="d-none d-md-flex" text href="#vendor">VENDORS</v-btn>

      <!-- Hamburger Menu Icon (Mobile) -->
      <v-app-bar-nav-icon class="d-md-none mr-5" @click="drawer = !drawer" />
      </v-app-bar>

    <!-- Mobile Drawer -->
    <v-navigation-drawer
      v-model="drawer"
      app
      temporary
      right
      class="d-md-none"
    >
      <v-list>
        <v-list-item link href="#The couple" @click="drawer = false">
          <v-list-item-title>THE COUPLE</v-list-item-title>
        </v-list-item>
        <v-list-item link href="#schedule" @click="drawer = false">
          <v-list-item-title>EVENT SCHEDULE</v-list-item-title>
        </v-list-item>
        <v-list-item link href="#gallery" @click="drawer = false">
          <v-list-item-title>GALLERY</v-list-item-title>
        </v-list-item>
        <v-list-item link href="#couple-story" @click="drawer = false">
          <v-list-item-title>COUPLE STORY</v-list-item-title>
        </v-list-item>
        <v-list-item link href="#message" @click="drawer = false">
          <v-list-item-title>MESSAGE</v-list-item-title>
        </v-list-item>
        <v-list-item link href="#vendor" @click="drawer = false">
          <v-list-item-title>VENDORS</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- Main Content -->
    <v-main>
      <div class="main-content">
        <div class="overlay-content">
          <h1 class="overlay-header">Step into heaven on earth, a place where God's love <br />thrives and victory is assured</h1>
          <p>Join us on our special day</p>
          <p>#JT25</p>
          <v-btn class="rsvp" @click="showRSVP = true">RSVP</v-btn>
        </div>
        <div id="The couple" class="nav"></div>
      </div>
    </v-main>

    <!-- RSVP Dialog -->
    <v-dialog v-model="showRSVP" max-width="500" max-height="500">
      <v-card>
        <img class="card-header-img" src="../assets/wedding invite.png" alt="invite" />
        <v-card-text>
          <p>We can't wait to share our special day with you! Please let us know if you'll be able to attend.</p>
          <v-radio-group v-model="rsvpResponse" row>
            <v-radio label="Yes, I'm coming!" value="YES"></v-radio>
            <v-radio label="No, I'm not coming." value="NO"></v-radio>
          </v-radio-group>
        </v-card-text>
        <v-card-actions>
          <v-btn color="success" @click="submitRSVP">Submit</v-btn>
          <v-btn text @click="showRSVP = false">Close</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-app>
</template>

<script>
import Toastify from "toastify-js";
import "toastify-js/src/toastify.css";
export default {
  components: { },
  name: 'Navbar',
  data() {
    return {
      drawer:false,
      showRSVP: false,
      rsvpResponse: '',
    }
  },
  methods: {
    submitRSVP(){
      if(this.rsvpResponse) {
        Toastify({
          text: `Thanks for your Response:  ${ this.rsvpResponse}`,
          duration: 3000,
          gravity: "top", 
          position: "center", 
          backgroundColor: "#4caf50", 
           style: {
          height: "90px", 
        },
          close: true, 
        }).showToast()
        this.showRSVP = false
      } else{
        alert('Please select an option before submitting')
      }
    }
  },
};

</script>

<style scoped>

.d-none {
  display: none;
}


.d-md-flex {
  display: flex;
}
.main-content{
  background-blend-mode: multiply;
  height: 100vh; 
  background-image: url('../assets/omo(23).jpg'); 
  background-size: cover;
  background-position: center;
  background-color: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: white;
}
.overlay-content {
  background-color: rgba(0, 0, 0, 0.1); 
  padding: 20px;
  border-radius: 10px;
  font-weight: bold;
  font-size: 1.5rem;
}
.rsvp{
  color: black;
}
.card-header{
  text-align: center;
  font-size: 2rem;
}
.card-header-img{
  height: 38vh;
}
 

@media (max-width: 600px) {
  .overlay-header{
    font-size: 2rem;
  }
}
</style>
