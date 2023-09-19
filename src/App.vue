<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <navigation-drawer v-model="drawer" />
      <v-text-field v-model="drawer"></v-text-field> 
      <v-spacer></v-spacer>
      <parent-component v-model="dialog"/>
    </v-main>
  </v-app>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';
import NavigationDrawer from './views/NavigationDrawer.vue';
export default {
  name: 'App',
  components: { NavigationDrawer, ParentComponent },
  data() {
    return {
      drawer: "Hello",
      dialog:false,
    }
  },
};
</script>
