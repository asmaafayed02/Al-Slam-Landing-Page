<template>
    <v-container>
      <v-app-bar app color="indigo-darken-3">
        <v-container>
          <v-row align="center">
            <v-col cols="auto">
              <v-toolbar-title>AL-SLAM</v-toolbar-title>
            </v-col>
            <v-spacer></v-spacer>
            <v-col cols="auto" class="hidden-sm-and-down">
              <v-btn text>Home</v-btn>
              <v-btn text>About</v-btn>
              <v-btn text>Contact</v-btn>
            </v-col>
            <v-col cols="auto" class="hidden-md-and-up">
              <v-menu >
                <template v-slot:activator="{ props }">
                  <v-btn icon="mdi-menu" v-bind="props">
                  </v-btn>
                </template>
                <v-list>
                  <v-list-item @click="navigateTo('home')">
                    <v-list-item-title>Home</v-list-item-title>
                  </v-list-item>
                  <v-list-item @click="navigateTo('about')">
                    <v-list-item-title>About</v-list-item-title>
                  </v-list-item>
                  <v-list-item @click="navigateTo('contact')">
                    <v-list-item-title>Contact</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>
            </v-col>
          </v-row>
        </v-container>
      </v-app-bar>
    </v-container>
  </template>
  

<script>
export default {
  name: 'NavBar',
  data:()=>({
    drawer: false,
      group: null,
  }),
  methods: {
    navigateTo(page) {
      // Here you can add your navigation logic, e.g., using Vue Router
      this.$router.push({ name: page });
    }
  }
};

</script>


