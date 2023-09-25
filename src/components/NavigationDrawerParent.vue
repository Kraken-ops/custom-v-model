<template>
  <div>
    <v-row class="justify-center d-flex ma-8">
      <v-btn
        class="button"
        style="z-index: 1"
        color="pink"
        dark
        @click.stop="drawer = !drawer"
      >
        <v-icon>mdi-tag-multiple</v-icon>
        Tags
      </v-btn>
    </v-row>

    <navigation-drawer-child v-model="drawer" drawerHeader=" Insert Header" v-slot:default="{data}">
      <!-- <template #default="slotProps">
        <p>{{ slotProps.content}}</p>
      </template> -->
      
    <p class="ml-4 mt-16">The text you have entered is <br> <strong>{{ data}}</strong></p>
  
    </navigation-drawer-child>
  </div>
</template>

<script>
import NavigationDrawerChild from "./NavigationDrawerChild.vue";
export default {
  components: { NavigationDrawerChild },
  data() {
    return {
      drawer: false,
    };
  },
};
</script>

<style>
.button {
  justify-content: center;
  display: flex;
}
</style>
