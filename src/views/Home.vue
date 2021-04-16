<template>
  <div class="home">
      <v-container>
        <v-row class="text-center mt-5 blue--text" justify="center">
          <h3>
            おすすめのTwitterアカウント共有アプリ
          </h3>
        </v-row>
        <v-row class="text-center mt-5 blue--text" justify="center">
          <h1>
            Twitterer
          </h1>
        </v-row>
      
        <v-row class="text-center mt-5 blue--text" justify="center">

          <router-link
            to="/search"
            class="text-decoration-none white--text font-weight-bold"
          >
          <v-btn
            color="blue"
            outlined
            class="font-weight-bold text--darken-2"
          >
            探す
          </v-btn>
          </router-link>
        </v-row>
        
        <v-row class="text-center mt-5 blue--text" justify="center">

          <router-link
            to="/add"
            class="text-decoration-none white--text font-weight-bold"
          >
          <v-btn
            color="blue"
            outlined
            class="font-weight-bold text--darken-2"
          >
            追加
          </v-btn>
          </router-link>
        </v-row>
      <router-view></router-view>
      </v-container>
      </div>
</template>

<script>

export default {
  name: 'Home',

  components: {
    
  },

  data: () => ({
    //
  }),
};
</script>
