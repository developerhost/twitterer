<template>
  <div class="about">
    <v-container>
      <v-row class="text-center mt-5 blue--text" justify="center">
        <h1>おすすめアカウント登録</h1>
      </v-row>

      <v-row class="text-center mt-5 blue--text" justify="center">
        <h3>アカウントの情報を登録してください</h3>
      </v-row>

      <v-row class="text-center mt-5 blue--text" justify="center">
        <v-text-field v-model="newAccountName" label="アカウント名" outlined></v-text-field>
      </v-row>
      <v-row class="text-center mt-5 blue--text" justify="center">
        <v-text-field v-model="newURL" label="アカウントのツイート" outlined></v-text-field>
      </v-row>

      <v-row class="text-center mt-5 blue--text" justify="center">
        <v-btn @click="addAccount()" color="blue" outlined class="font-weight-bold text--darken-2">
          次へ
        </v-btn>
      </v-row>

      <v-row dense>
        <v-col v-for="(account, key) in accounts" :key="key" cols="12">
          {{ account }}
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import firebase from "firebase";

export default {
  name: "Add",
  data: () => ({
    db: null,
    accountsRef: null,
    newAccountName: "",
    newURL: "",
    accounts: {}
  }),
  created() {
    this.db = firebase.firestore();
    this.accountsRef = this.db.collection("accounts");
    this.accountsRef
      .onSnapshot((querySnapshot) => {
        const obj = {};
        querySnapshot.forEach((doc) => {
          obj[doc.id] = doc.data();
        });
        this.accounts = obj;
      });
      console.log(process.env.VUE_APP_APIKEY);
      
  },
  methods: {
    addAccount() {
      // ここは下に赤い表示が出るようにする
      if (this.newAccount === "") {
        alert("入力してください");
      } else {
        this.accountsRef.add({
          accountName: this.newAccountName,
          accountURL: this.newURL
        })
      }
    }
  }
}
</script>
