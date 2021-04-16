<template>
  <v-app>
    <v-main>
      <v-container>
        <div id="app">
          <div id="nav"></div>
          <router-view />
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    //
  }),
};
</script>
