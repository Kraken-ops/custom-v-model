<template>
  <child-component :newValue="dialog" @emittedEvent="dialog = $event"/>
</template>

<script>
import ChildComponent from './ChildComponent.vue'
export default {
  components: { ChildComponent },
  data() {
    return {
      dialog:false,
    }
  },

}
</script>

<style>

</style>