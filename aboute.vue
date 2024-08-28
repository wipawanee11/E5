<template>
    <v-app>
      <!-- Hero Image -->
      <v-img
        src="https://inwfile.com/s-ca/ovsq8q.jpg"
        
        class="hero-image"
      >
        <v-container fill-height style="">
          <v-row align="center" justify="center" class="fill-height">
            <v-col > <br><br><br><br><br><br><br><br><br>
              <v-card class="text-center hero-card" elevation="8">
                <v-card-title class="headline white--text">Hello, my name is Wipawanee Yotsang.</v-card-title>
                <v-card-title class="headline white--text">My hobbies are eating and raising cats. I like to eat sweets, cook, and travel. I am 19 years old.</v-card-title>
                <v-card-title class="headline white--text">I study Information Technology. I was born in Chaiyaphum. Thank you.</v-card-title>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-img>
  
      <!-- Main Content
      <v-main>
        <v-container class="pa-5">
          <v-card class="bg-blur">
            <v-card-title>Content Title</v-card-title>
            <v-card-text>
              This is where you put the content of your page.
            </v-card-text>
          </v-card>
        </v-container>
      </v-main> -->
    </v-app>
  </template>
  
  <script>
  export default {
    name: 'hsome',
  };
  </script>
  
  <style scoped>
  .hero-image {
    position: relative;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
  }
  
  .hero-card {
    position: relative;
    padding: 16px;
    background: rgba(255, 255, 255, 0.5); /* Semi-transparent background for the text */
  }
  
  .bg-blur {
    backdrop-filter: blur(10px); /* Apply blur effect */
    -webkit-backdrop-filter: blur(10px); /* For Safari support */
    background: rgba(255, 255, 255, 0.6); /* Semi-transparent white background for contrast */
  }
  </style>