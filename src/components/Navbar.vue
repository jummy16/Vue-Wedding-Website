<template>
    
  <v-app>
    <v-app-bar app >
      <v-toolbar-title>
        <img src="../assets/JT wedding logo.webp" alt="Wedding Logo" height="50">
      </v-toolbar-title>
      
      <v-spacer></v-spacer>
      
      <v-btn text href="#The couple">THE COUPLE</v-btn>
      <v-btn text href="#schedule">EVENT SCHEDULE</v-btn>
      <v-btn text>GALLERY</v-btn>
      <v-btn text>COUPLE STORY</v-btn>
      <v-btn text>MESSAGE</v-btn>
      <v-btn text>VENDORS</v-btn>
    </v-app-bar>

    
    <v-main>
        <div class="main-content">
          <div class="overlay-content">
            <h1>Step into heaven on earth, a place where God's love <br/>thrives and victory is assured</h1>
            <p>Join us on our special day</p>
            <p>#JT25</p>
            <v-btn class="rsvp" @click="showRSVP= true">RSVP</v-btn>
          </div>
          <div id="The couple" class=nav></div>
        </div>
    </v-main>

    <v-dialog v-model="showRSVP" max-width='500' max-height='500'>
      <v-card>
        <!-- <v-card-title class="card-header">You're Invited!</v-card-title> -->
        <img class="card-header-img" src="../assets/wedding invite.png" alt="invite">
        <v-card-text>
          <p>We can't wait to share our special day with you! Please let us know if you'll be able to attend.</p>
           <v-radio-group v-model="rsvpResponse" row>
            <v-radio label="Yes, I'm coming!" value="YES"></v-radio>
            <v-radio label="No, I'm coming." value="NO"></v-radio>
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
</style>
