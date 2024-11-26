<template>
  <div id="message"></div>
  <v-container class="message-page" fluid>
    <v-row>
      <!-- Form for submitting a message -->
      <v-col cols="12" sm="6" offset-sm="3">
        <v-form @submit.prevent="submitMessage">
          <v-textarea
            v-model="newMessage"
            label="Leave a message for the couple"
            outlined
            rows="3"
            placeholder="Write your message..."
          ></v-textarea>
          <v-btn type="submit" color="secondary">Submit Message</v-btn>
        </v-form>
      </v-col>
    </v-row>

    <!-- Displaying Guest Messages -->
    <v-row class="messages-container">
      <transition-group name="fade-slide" tag="div">
        <v-col
          v-for="message in messages"
          :key="message.id"  
          cols="auto"
          class="message-item"
        >
          <v-card class="message-card" :elevation="2">
            <img class="emoji" src="../assets/love-emoji.jfif" alt="love-emoji">
            <v-card-subtitle>{{ message.date }}</v-card-subtitle>
            <v-card-text>{{ message.text }}</v-card-text>
          </v-card>
        </v-col>
      </transition-group>
    </v-row>
  </v-container>
</template>




<script>
export default {
  data() {
    return {
      newMessage: '',
      messages: [],
    };
  },
  mounted() {
    this.loadMessages(); // Load messages when the component is mounted
  },
  methods: {
    submitMessage() {
      if (this.newMessage.trim()) {
        const newMessage = {
          date: new Date().toLocaleDateString(),
          text: this.newMessage,
        };
        this.messages.push(newMessage);
        this.saveMessages(); // Save to localStorage
        this.newMessage = ''; // Clear input field
      }
    },
    loadMessages() {
      const storedMessages = JSON.parse(localStorage.getItem('messages'));
      if (storedMessages) {
        this.messages = storedMessages; // Load messages from localStorage if available
      }
    },
    saveMessages() {
      localStorage.setItem('messages', JSON.stringify(this.messages)); // Save messages to localStorage
    }
  },
};
</script>



<style scoped>
.message-page {
  background-color: #E6CCE6;
  padding: 30px;
}

.v-btn {
  margin-top: 10px;
}

.emoji {
  width: 10%;
  margin-left: 7rem;
  margin-top: 0.5rem;
}

.messages-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start; /* Align horizontally */
}

.message-item {
  margin: 10px;
  display: inline-block;
  max-width: 600px; 
  transition: transform 0.3s ease;
  transform: translateX(0);
}

.message-card {
  background-color: #fff;
}

.v-row {
  margin-top: 20px;
}

/* Animation for messages */
.fade-slide-enter-active,
.fade-slide-leave-active {
  transition: transform 0.5s ease, opacity 0.5s ease;
}

.fade-slide-enter, 
.fade-slide-leave-to /* .fade-slide-leave-active in <2.1.8 */ {
  transform: translateX(50px);
  opacity: 0;
}

.fade-slide-leave-to {
  transform: translateX(-50px);
  opacity: 0;
}
</style>


