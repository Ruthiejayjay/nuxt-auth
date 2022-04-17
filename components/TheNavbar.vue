<template>
  <v-app-bar app color="green">
    <!-- Home Page -->
    <nuxt-link to="/">
      <v-img
        src="https://vue-screencasts-uploads.s3-us-west-2.amazonaws.com/vuescreencasts-logo-small.jpg"
        to="/"
      />
    </nuxt-link>

    <v-btn to="/" text>VueScreencasts</v-btn>

    <v-spacer />
    <div v-if="$auth.loggedIn">
      {{ $auth.user.email }}
      <v-btn text>Logout</v-btn>
      <!-- username -->
      <!-- logout button --->
    </div>
    <div v-else>
      <v-btn text to="/login">Login</v-btn>
            <v-btn text to="/register">Register</v-btn>
      <!-- login -->
      <!-- logout -->
    </div>
    <!-- Desktop menu -->
   
   
  
    <!-- <v-btn
      v-for="link in authLinks"
      :key="link.name"
      text
      right
      :to="link.to"
      class="hidden-sm-and-down"
      @click="link.click ? link.click() : null"
    >
      {{ link.text }}
    </v-btn> -->

    <!-- Mobile menu -->
    <v-menu>
      <template #activator="{ on }">
        <v-btn icon v-on="on" class="hidden-md-and-up">
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="link in mobileLinks"
          :key="link.text"
          :to="link.to"
          text
          @click="link.click ? link.click() : null"
        >
          <v-list-item-title>{{ link.text }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </v-app-bar>
</template>

<script>
export default {
  computed: {
    navLinks() {
      let links = [
        { text: "Courses", to: "/courses" },
        { text: "Archive", to: "/videos" },
      ];
      return links;
    },
  },
};
</script>

<style lang="scss" scoped>
.v-image,
img {
  border-radius: 50% !important;
  width: 45px;
  margin-right: 5px;
  margin-top: 5px;
  display: inline-block;
}
</style>