<template>
  <v-app>
    <v-toolbar dark color="purple" class="hidden-xs-and-down header shrink">
        <v-toolbar-title>Storespy Frontend Challenge</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items>
         <v-btn
           v-for="item in nav"
           :key="item.icon"
           :to="item.to"
           :title="item.title"
         >{{ item.text }}</v-btn>
        </v-toolbar-items>
    </v-toolbar>
    <main>
      <v-container>
        <Nuxt />
      </v-container>
    </main>
  
    
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      nav: [
        {
          text: 'Home',
          active: true,
          to:"/"
        },
        {
          text: 'Posts',
          active: false,
          to: "/posts"
        },
        {
          text: 'Contact',
          active: false,
          to: "/contact"
        }
      ],
      title: 'Vuetify.js'
    }
  }
}
</script>
<style lang="css">
.v-toolbar__items a{
  background:#fff !important;
  color: #5b009b !important;
}
</style>