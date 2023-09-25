<template>
  <v-sheet
    height="90vh"
    class="overflow-hidden"
    style="position: absolute; width: 98vw; top: 10px"
  >
    <!-- <v-container class="fill-height">
      
    </v-container> -->

    <v-navigation-drawer v-model="drawer" absolute right bottom class="border">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title
            >{{ drawerHeader }}
            <v-btn absolute icon right color="blue darken-2"  @click="drawer = false">
              <v-icon class="mb-4">mdi-close</v-icon>
            </v-btn>
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
            <v-row class="ml-2 mt-1">
              <v-col cols="24" sm="30">
                <v-text-field
                  v-model="message"
                  label="Search Tags"
                  append-icon="mdi-magnify"
                  clearable
                  autofocus
                  @keyup.13="sendData"
                ></v-text-field>
              </v-col>
            </v-row>
          </v-container>
        </v-form>
      <!-- <slot name="default" :message="sendData"> 
        <p class="ml-16 mt-16">Drawer Body</p>
      </slot> -->
      <div>
        <slot :data="slotMessage"></slot>
      </div>
      <!-- <slot name="default" :message="content"></slot> -->
    </v-navigation-drawer>
  </v-sheet>
</template>

<script>
export default {
  props: {
    value: {
      default: false,
      type: Boolean,
    },
    drawerHeader: {
      default: "Default Value",
      type: String,
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
      slotMessage: "",
      items: [
        { title: "Home", icon: "mdi-view-dashboard" },
        { title: "About", icon: "mdi-forum" },
      ],
    };
  },
  methods: {
    sendData()
    {
      this.slotMessage=this.message;
    }
  },
  
};
</script>

<style>
.border {
  border-style: solid;
  border-width: 1px;
}
</style>
