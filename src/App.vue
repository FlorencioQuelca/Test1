<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
      APP TEST 1
      </div>
      <v-spacer></v-spacer>
      <v-btn
        href="https://github.com/FlorencioQuelca/Test1.git"
        target="_blank"
        text
      >
        <span class="mr-2">github of florencio Quelca</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
      </v-app-bar>
    <v-main class="grey lighten-2">
      <v-container>
      <router-view/>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
