<template>
  <v-app>
    <v-toolbar dark color="purple" class="hidden-sm-and-down header shrink">
        <v-toolbar-title>{{menuTitle}}</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items>
         <v-btn
           v-for="item in nav"
           :key="item.to"
           :to="item.to"
           :title="item.title"
         >{{ item.text }}</v-btn>
        </v-toolbar-items>
    </v-toolbar>
    <v-toolbar dark color="purple" class="hidden-md-and-up shrink">
      <v-toolbar-title>{{menuTitle}}</v-toolbar-title>
      <v-spacer></v-spacer>

      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn dark icon v-bind="attrs" v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>
        <v-list class="mobile--menu">
          <v-list-item v-for="item in nav" :key="item.to">
            <v-list-item-title>
              <nuxt-link :to="item.to">{{ item.text }}</nuxt-link>
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu> 
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
      dialog: false,
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
      menuTitle: 'Storespy Frontend Challenge'
    }
  }
}
</script>
<style lang="css">
.v-toolbar__items a{
  background:#fff !important;
  color: #5b009b !important;
}
.mobile--menu a{
  text-decoration: none;
  color: #5b009b !important;
}
</style>