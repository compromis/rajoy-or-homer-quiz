<template>
  <div class="background" :style="{ transform: 'scale(' + zoom + ')' }"></div>
</template>

<script>
export default {
  name: 'background',

  data () {
    return {
      zoom: 1,
      ticking: false,
      last_known_scroll_position: 0
    }
  },

  created () {
    window.addEventListener('scroll', this.onScroll)
  },

  destroyed () {
    window.removeEventListener('scroll', this.onScroll)
  },

  methods: {
    onScroll (event) {
      this.last_known_scroll_position = window.scrollY
      let self = this
      if (!this.ticking) {
        window.requestAnimationFrame(function () {
          if (self.last_known_scroll_position < 600) {
            self.zoom = 1 + (self.last_known_scroll_position * 0.25 / 600)
          }

          self.ticking = false
        })

        this.ticking = true
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../variables';

.background {
  position: fixed;
  background-image: url(../assets/images/background.jpg);
  background-size: 100%;
  background-repeat: no-repeat;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  right: 0;
  z-index: 0;
  transform: 0.15s ease-in-out;
}
</style>
