<template>
  <v-container>
      <h1>Login</h1>

      <UserAuthForm buttonText="Login" />
  </v-container>
</template>

<script>
import UserAuthForm from '@/components/UserAuthForm.vue'
export default {
    components:{
        UserAuthForm
    },
    // methods:{
    //     loginUser(logininfo){
    //         this.$auth.loginWith('local',{
    //             data: logininfo
    //         })
    //         //alert('You pressed a button')
    //     }
    // }
}
</script>

<style>

</style>