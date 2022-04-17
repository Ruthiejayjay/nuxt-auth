<template>
  <v-container>
    <h1>Register</h1>
    <UserAuthForm
      buttonText="Register"
      :hasName="true"
    />
  </v-container>
</template>

<script>
import UserAuthForm from "@/components/UserAuthForm.vue";
export default {
  components: {
    UserAuthForm,
  },

};
</script>

<style>
</style>