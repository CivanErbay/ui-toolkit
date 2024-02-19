<template>
  <v-app-bar app color="primary">
    <v-spacer></v-spacer>

    <v-toolbar-items class="center">
      <router-link to="/"> <v-btn text>Vuetify</v-btn></router-link>
      <router-link to="/tailwind">
        <v-btn text>Tailwind</v-btn>
      </router-link>
      <router-link to="/elementplus">
        <v-btn text>Element Plus</v-btn>
      </router-link>
    </v-toolbar-items>
    <v-spacer></v-spacer>
  </v-app-bar>
</template>

<script>
export default {
  name: 'Navbar'
}
</script>

<style scoped>
.v-app-bar__toolbar {
  justify-content: center;
}
.center {
  display: flex;
  align-items: center;
}
</style>
