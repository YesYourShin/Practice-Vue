<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark>
        <h1>Books</h1>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',
};
</script>
