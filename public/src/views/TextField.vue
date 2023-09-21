<template>
    <v-card>
      <v-text-field v-model="drawer"></v-text-field>
      <v-btn @click="onChangeText">Update Text</v-btn>
    </v-card>
  </template>
  
  <script>
  export default {
    data() {
      return {
       
      };
    },
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
    methods: {
        onChangeText() {
            this.drawer = "This is updated value from component itself"
        }
    },
  };
  </script>
  
  <style>
  </style>