<template>
  <v-sheet height="400" class="overflow-hidden" style="position: relative">
    <!-- <v-container class="fill-height">
      
    </v-container> -->

    <v-navigation-drawer v-model="drawer" absolute right bottom class="border">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title
            >Associate Tags
            <v-icon
              color="blue darken-2"
              class="ml-16 pl-4"
              @click="drawer = false"
              >mdi-close</v-icon
            >
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <!-- <v-list dense>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list> -->

      
        <v-form>
          <v-container>
            <v-row class="ml-2 mt-8">
              <v-col cols="24" sm="30">
                <v-text-field
                  v-model="message"
                  label="Search Tags"
                  append-icon='mdi-magnify'
                  clearable
                  autofocus
                ></v-text-field>
              </v-col>
            </v-row>
          </v-container>
        </v-form>
    </v-navigation-drawer>
  </v-sheet>
</template>

<script>
export default {
  props: {
    value: {
      default: "",
      type: Boolean,
    },
  },
  computed: {
    drawer: {
      get: function () {
        return this.value;
      },
      set: function (newValue) {
        this.$emit("input", newValue);
      },
    },
  },
  data() {
    return {
        message: "",
      items: [
        { title: "Home", icon: "mdi-view-dashboard" },
        { title: "About", icon: "mdi-forum" },
      ],
    };
  },
};
</script>

<style>
.border{
    border-style: solid;
    border-width: 1px;
}
</style>
