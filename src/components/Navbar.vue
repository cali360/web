<template>
  <nav>
    <v-toolbar app dark color="primary">
      <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title class="headline text-uppercase">
          <span class="font-weight-light">CALI </span>
          <span>360</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
          flat
          href="https://github.com/vuetifyjs/vuetify/releases/latest"
          target="_blank">
          <span class="mr-2">Latest Release</span>
      </v-btn>
    </v-toolbar>

    <v-navigation-drawer v-model="drawer" app class="primary">
      <v-list>
        <v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
          <v-list-tile-action>
            <v-icon class="white--text">{{ link.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="white--text">{{link.text}}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
      
  </nav>
    
</template> 


<script>
export default {
  data() {
    return {
      drawer: true,
      links: [
        { icon: 'dashboard', text: 'Dashboard', route: '/'},
        { icon: 'person', text: 'Team', route: '/team'}
      ]
    }
  }
    
}
</script>
