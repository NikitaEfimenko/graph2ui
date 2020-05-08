<template>
  <v-app id="app">
    <router-view></router-view>
    <v-bottom-navigation
      app
      v-model="nav"
      dark
    >
      <v-btn
        v-for='tab in tabs' 
        :to='tab.path'
        :key='tab.id'
      >
        <span>{{tab.name}}</span>
        <v-icon>mdi-book</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      nav: null,
      tabs: [{{ROUTES_TO_TABS}}]
    }
  }
}
</script>

<style>
html, body, #app {
  height: 100%;
  width: 100%;
}

#app {
  font-family: 'Roboto', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
