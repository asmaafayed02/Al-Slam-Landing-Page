<template>
    <v-container>
      <v-row justify="center" v-if="loading">
        <v-col cols="12" class="text-center">
          <v-progress-circular
            indeterminate
            color="primary"
          ></v-progress-circular>
        </v-col>
      </v-row>
      <v-row v-else>
        <v-col
          v-for="chapter in chapters"
          :key="chapter.id"
          cols="12"
          md="4"
        >
          <v-card
            class="mx-auto chapter-card"
            max-width="344"
            hover
          >
            <v-card-title class="font-weight-bold">
              {{ chapter.name_simple }} - {{ chapter.name_arabic }}
            </v-card-title>
            <v-card-subtitle>
              ({{ chapter.translated_name.name }})
            </v-card-subtitle>
            <v-card-text>
              Revelation Place: {{ chapter.revelation_place }}<br />
              Verses Count: {{ chapter.verses_count }}
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  
  <script>
  export default {
    name: 'QChapters',
    data() {
      return {
        chapters: [],
        loading: true, // Add a loading state
      };
    },
    mounted() {
      this.fetchChapters();
    },
    methods: {
      async fetchChapters() {
        try {
          const response = await fetch('https://api.quran.com/api/v4/chapters');
          const data = await response.json();
          this.chapters = data.chapters;
        } catch (error) {
          console.error('Error fetching chapters:', error);
        } finally {
          this.loading = false; // Set loading to false after fetching data
        }
      }
    }
  };
  </script>
  
  
  <style scoped>
  .v-container {
    margin-top: 20px;
  }
  .chapter-card {
    transition: background-color 0.3s ease;
  }
  .chapter-card:hover {
    background-color: #473cc5; /* Change this to your desired hover color */
    color: white;
  }
  </style>
  
  