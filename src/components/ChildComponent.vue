<template>
    <div class="text-center">
      <v-dialog v-model="dialog" width="500">
        <template v-slot:activator="{ on, attrs }">
          <v-btn style="z-index: 1; margin-top: 10px;" color="blue darken-2" dark v-bind="attrs" v-on="on">
            Click Me
          </v-btn>
        </template>
  
        <v-card>
          <span>
            <v-card-title class="pl-8 text-h5 blue lighten-4" >
              Privacy Policy
              <v-icon large color="blue darken-2" id="icon" @click="dialog = false">mdi-close</v-icon>
            </v-card-title>
            
          </span>
  
          <v-card-text>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
            minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
            culpa qui officia deserunt mollit anim id est laborum.
          </v-card-text>
  
          <v-divider></v-divider>
  
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="primary" text @click="dialog = false"> I accept </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
  </template>
  <script>
  export default {
      props: {
          newValue: {
              type: Boolean,
              default: false,
          },
      },
      computed: {
          dialog: {
          get: function () {
            return this.newValue;
          },
          set: function (val) {
            this.$emit("emittedEvent", val);
          },
        },
      },
    data() {
      return {
        
      };
    },
  };
  </script>
  
  <style>
  #icon{
      margin-bottom: -8px;
      margin-left: 250px;
  }
  </style>
  