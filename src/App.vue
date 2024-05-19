<template>
  <v-app>
          <NavBar/>
          <router-view></router-view>
          <v-main>
            <v-content>
            <QChapters/>
          </v-content>
          </v-main>

    </v-app>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import NavBar from './components/NavBar.vue'
import QChapters from './components/Chapters.vue'
export default {
  name: 'App',
  components: {
    NavBar,
    QChapters,  
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
