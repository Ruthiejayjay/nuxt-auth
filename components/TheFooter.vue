<template>
  <v-footer padless>
    <v-card
      text
      tile
      width="100%"
    >
      <v-card-title>
        <div>Copyright 2019-2020 Happy Programmer LLC</div>

        <v-spacer />
        
        <div class="icons">
          <a href="https://twitter.com/VueScreencasts" target="_blank">
          </a>
          &nbsp;
          <a href="https://www.youtube.com/channel/UCJasK7cAgRz1RGMJCoRLXXQ/" target="_blank">
    
          </a>
          &nbsp;
          <a href="https://www.instagram.com/vue_training/" target="_blank">

          </a>
          &nbsp;
          <a href="https://www.facebook.com/VueTrainingnet-115924840200999" target="_blank">

          </a>
          &nbsp;
          <a href="https://www.linkedin.com/company/vuetraining/" target="_blank">

          </a>
          &nbsp;
          <a href="https://dev.to/vuetraining" target="_blank">

          </a>

        </div>
        
        <v-spacer />
        
        <nuxt-link to="/policies/terms-and-conditions">Terms and Conditions</nuxt-link>
        <nuxt-link to="/policies/privacy-policy">Privacy Policy</nuxt-link>
        <a href="mailto:jeffrey@vuescreencasts.com" target="_blank">Contact Me</a>
        <!-- <nuxt-link to="policies">View All Policies</nuxt-link> -->
      </v-card-title>
    </v-card>
  </v-footer>
</template>

<script>
  export default {
    
  }
</script>

<style lang="scss" scoped>
  .v-card__title {
    font-size: 100%;
    a {
      margin-right: 9px;
    }
  }
  .icons svg {
    font-size: 1.1em;
  }
</style>