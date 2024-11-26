<template>
<div id="vendor"></div>
  <v-container fluid class="vendors-page">
    <v-row class="vendors-row">
      <v-col
        v-for="(vendor, index) in vendors"
        :key="index"
        cols="12" sm="6" md="4" lg="3"
        class="vendor-item"
      >
        <!-- Vendor Card -->
        <v-card class="vendor-card" elevation="2">
          <v-card-title>{{ vendor.name }}</v-card-title>
          <v-card-subtitle>{{ vendor.description }}</v-card-subtitle>
          <v-card-actions>
            <v-btn
              color="red"
              href="vendor.instagram"
              target="_blank"
              icon
            >
              <v-icon>mdi-instagram</v-icon>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>


<script>
export default {
  data() {
    return {
      vendors: [
        {
          name: "Exquisite Event",
          description: "Event Planner",
          instagram: "https://www.instagram.com/official_exquisiteevents?igsh=MWFoMzJrdXE4Y21nZQ==",
        },
        {
          name: "Global View",
          description: "Photography Services",
          instagram: "https://www.instagram.com/official_exquisiteevents?igsh=MWFoMzJrdXE4Y21nZQ==",
        },
        {
          name: "Times and Season",
          description: "Catering Services",
          instagram: "https://www.instagram.com/vendor3",
        },
        {
          name: "OBS Consult",
          description: "Security",
          instagram: "https://www.instagram.com/vendor4",
        },
         {
          name: "Ronnie Decor",
          description: "Decorator",
          instagram: "https://www.instagram.com/vendor5",
        },
         {
          name: "Mthrisa",
          description: "Makeover",
          instagram: "https://www.instagram.com/vendor6",
        },
         {
          name: "Jaybest",
          description: "MC/Hypeman",
          instagram: "https://www.instagram.com/vendor7",
        },
         {
          name: "House of Beauty",
          description: "Wedding Gown",
          instagram: "https://www.instagram.com/vendor8",
        },
         {
          name: "Fujicologist",
          description: "Live Band",
          instagram: "https://www.instagram.com/vendor9",
        },
        {
          name: "DJ Splash",
          description: "DJ",
          instagram: "https://www.instagram.com/vendor10",
        },
        {
          name: "Honeydrops",
          description: "Cake",
          instagram: "https://www.instagram.com/vendor11",
        },
        {
          name: "Ghrazefoodies",
          description: "Small chops/Cocktail/Grills",
          instagram: "https://www.instagram.com/vendor4",
        },
      ]
    };
  }
};
</script>


<style scoped>
.vendors-page {
  padding: 30px;
  background-color: #f8f8f8;
}

.vendors-row {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

.vendor-item {
  margin: 15px;
  text-align: center;
}

.vendor-card {
  border-radius: 8px;
}

.vendor-card .v-card-title {
  font-weight: bold;
  font-size: 1.2rem;
}

.vendor-card .v-card-subtitle {
  color: #555;
  margin-bottom: 15px;
}

.v-btn {
  margin-top: 10px;
  width: 100%;
}
</style>
