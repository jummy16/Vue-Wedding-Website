<template>
<div id="couple-story"></div>
  <v-container class="couple-story-page" fluid>
    <v-carousel 
      cycle 
      hide-delimiters 
       hide-delimiter-background
      height="600px"
      interval="9000"
    >
      
      <v-carousel-item>
        <v-row class="d-flex align-center justify-content couple-picture">
          
          <v-col cols="6">
            <v-img 
              :src="stories[0].image" 
              alt="Bride's Picture"
              height="100%"
              width="70%"
              contain
            />
          </v-col>
          <!-- Bride's Story -->
          <v-col cols="6" class="story-container">
            <div class="story">
              <h2 class="text-h4">{{ stories[0].name }}</h2>
              <p>{{ stories[0].story }}</p>
            </div>
          </v-col>
        </v-row>
      </v-carousel-item>

      
      <v-carousel-item>
        <v-row class="d-flex align-center couple-picture">
          
          <v-col cols="6">
            <v-img 
              :src="stories[1].image" 
              alt="Groom's Picture"
              height="100%"
              width="70%"
              contain
            />
          </v-col>
          <!-- Groom's Story -->
          <v-col cols="6" class="story-container">
            <div class="story">
              <h2 class="text-h4">{{ stories[1].name }}</h2>
              <p>{{ stories[1].story }}</p>
            </div>
          </v-col>
        </v-row>
      </v-carousel-item>
    </v-carousel>
  </v-container>
</template>

<script>
import bridepicture from '../assets/omo(119).jpg'
import groompicture from '../assets/omo(129).jpg'
export default {
  data() {
    return {
      stories: [
        {
          name: "The Bride",
          image:(bridepicture), 
          story:"Let me tell you about him……I’ve always known that to call him my ‘best friend’ was an understatement’…there’s a better word for it… A man of character, he knows the meaning of giving, the meaning of self-sacrifice. A man of deep insight, he has made me understand life in all it’s different angles, all it’s sides.He has helped me value who I am, the way he sees me gives me confidence and encourages me to be better. He sets examples and pushes you to your full capability. I don’t only speak for myself but I speak for all those he’s influenced. He’s taught me so much about what a person should be; in giving more of yourself and in loving, you truly live!"
        },
        {
          name: "The Groom",
          image:(groompicture),
          story: "She was kind, intelligent, good natured and idealistic. I could not help but think her naïve. But she was far from it. Her disposition was so positive, her faith so strong, so deeply rooted in truth, that my pessimism, cynicism and criticism were all equally unsuccessful in disarming it. I tried unrelentingly. I challenged her notions of goodness and virtue. But her mind was sharp, quick to debunk my views.  My agnostic temperament and sarcasm were no match for her, as she defended her faith, while restoring mine.  By the end of each argument, I was embarrassed of how silly and childish I must have sounded.   We became good friends. I trusted her with my life. She felt like “home”, I felt so comfortable around her, that feeling I can only describe as joy."
        },
      ]
    };
  }
};
</script>

<style scoped>
.couple-story-page {
  padding: 20px;
  background-color: #fffbf2;
  margin: 2rem;
}
 
.v-carousel-item {
  display: flex;
  align-items: center;
  justify-content: center;
  height: auto;
}

.v-carousel {
  border-radius: 8px;
  overflow: hidden;
  margin: 0;
  padding: 0;
}

h2 {
  margin-bottom: 10px;
  color: black;
}

p {
  font-size: 1.1rem;
  line-height: 1.6;
  color: #555;
}

.story {
  max-width: 100%;
  overflow: visible;
  word-wrap: break-word;
  margin-right: 15rem;
  justify-content: center;
  line-height: 1.8;
}

@media (max-width: 600px) {
  .couple-picture {
    flex-direction: column; 
    align-items: flex-start; 
    padding: 0 10px; 
  }

  .story-container {
    max-width: 100%; 
    margin: 0;
    padding: 0;
    text-align: left;
  }

  .story {
    padding: 0 10px; 
    text-align: left;
    margin-right: 2rem;
  }
   
}

</style>

