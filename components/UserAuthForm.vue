<template>
  <v-form v-model="valid">
    <v-text-field
      v-model="userInfo.name"
      label="Name"
      color="green"
      :rules="[required('name')]"
      v-if="hasName"
    />

    <v-text-field
      v-model="userInfo.email"
      label="Email"
      color="green"
      :rules="[required('email'), emailFormat()]"
    />

    <v-text-field
      v-model="userInfo.password"
      label="Password"
      counter="true"
      :rules="[required('password'), minLength('password', 8)]"
    />

    <v-btn @click="register()" :disabled="!valid" color="green accent-3">{{
      buttonText
    }}</v-btn>
  </v-form>
</template>

<script>
import validations from "@/utils/validations";
export default {
  data() {
    return {
      valid: false,
      userInfo: {
        name: "",
        email: "",
        password: "",
      },
      ...validations,
    };
  },

  props: ["submitForm", "buttonText", "hasName"],
  methods: {
    register() {
      var axios = require("axios");
      var data = JSON.stringify({
        email: this.userInfo.email,
        password: this.userInfo.password,
        name: this.userInfo.name,
      });

      var config = {
        method: "post",
        url: "https://api.backendless.com/AC9327EA-2333-7B20-FFFC-EEF5EA3E6600/CE07712A-27DD-4015-A12F-3DAAE010EE1E/users/register",
        headers: {
          "Content-Type": "application/json",
        },
        data: data,
      };

      axios(config)
        .then(function (response) {
          console.log(JSON.stringify(response.data));
        })
        .catch(function (error) {
          console.log(error);
        });
    },

    login() {
      var axios = require("axios");
      var data = JSON.stringify({
        login: "test@mailinator.com",
        password: "12345678",
      });

      var config = {
        method: "post",
        url: "https://api.backendless.com/AC9327EA-2333-7B20-FFFC-EEF5EA3E6600/CE07712A-27DD-4015-A12F-3DAAE010EE1E/users/login",
        headers: {
          "Content-Type": "application/json",
        },
        data: data,
      };

      axios(config)
        .then(function (response) {
          console.log(JSON.stringify(response.data));
        })
        .catch(function (error) {
          console.log(error);
        });
    },

    // async registerUser(registrationinfo){
    //     await this.$axios.post('local', registrationinfo)
    //      this.$auth.loginWith('local',{
    //         data: registrationinfo
    //     })
    //     alert('You pressed a button')
    // }
  },
};
</script>

<style lang="scss" scoped>
</style>