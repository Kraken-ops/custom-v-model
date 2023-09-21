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
      <!-- <TextField v-model="drawer" />
      <v-text-field v-model="drawer"></v-text-field>  -->
      <v-spacer></v-spacer>
     <!-- 
        /**
      Documentation guide to write custom v-model directives
      https://learnvue.co/articles/v-model-guide
       */
     --> 
      <parent-component />
      <v-spacer></v-spacer>
      
      <navigation-drawer-parent />
    </v-main>
  </v-app>
</template>

<script>
import NavigationDrawerParent from './components/NavigationDrawerParent.vue';
import ParentComponent from './components/ParentComponent.vue';
import TextField from './views/TextField.vue';
export default {
  name: 'App',
  components: { TextField, ParentComponent, NavigationDrawerParent },
  data() {
    return {
      drawer: "Hello",
    }
  },
};
</script>
