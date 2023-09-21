<template>
  <div>
    <v-row class="justify-center d-flex ma-8">
        <v-btn class="button" color="pink" dark @click.stop="drawer = !drawer">
        <v-icon>mdi-tag-multiple</v-icon>
        Tags
      </v-btn>
    </v-row>
      
    <navigation-drawer-child v-model="drawer"></navigation-drawer-child>
    
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
.button{
    justify-content: center;
    display: flex;
}
</style>
