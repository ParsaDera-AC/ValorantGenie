<template>
  <v-app>
    <v-app-bar app color="#232323" dark>
      <v-container>
        <div class="row">
          <div class="col">
            <h1 class="text-left" style="color: #f1f1f1">Valorant Genie</h1>
          </div>
        </div>
      </v-container>
      <v-spacer></v-spacer>
    </v-app-bar>
    <br />
    <v-main style="background-color: #121212; color: #f1f1f1">
      <v-container fluid>
        <v-row class="d-flex justify-left align-center">
          <v-col cols="12" md="8">
            <FirstAPI />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import FirstAPI from "./components/FirstAPI.vue";

export default {
  name: "App",
  components: {
    FirstAPI,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.dark-bg {
  background-color: #232323;
}

/* Add some padding and a box shadow to the app bar */
.v-app-bar {
  padding: 1em;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
/* Add some padding and a border to the main content area */
.v-main {
  padding: 1em;
  border: 2px solid #f1f1f1;
  border-radius: 1em;
}
/* Add some hover effect to the navigation links */
.v-app-bar .v-btn {
  transition: all 0.3s ease;
}
.v-app-bar .v-btn:hover {
  transform: scale(1.1);
}
</style>
