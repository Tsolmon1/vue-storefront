<template>
  <div class="overlay" @click="onClick" v-if="isVisible">
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'overlay',
  computed: mapState({
    isVisible: state => state.ui.overlay
  }),
  methods: {
    onClick () {
      this.$store.commit('ui/setOverlay', false)
    }
  }
}
</script>

<style scoped>
.overlay {
    width: 100%;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    background: rgba(0,0,0,.4);
    z-index: 3;
}
</style>
