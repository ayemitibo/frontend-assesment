<template>
  <transition :name="name" v-bind="$attrs">
    <slot v-if="shown" />
  </transition>
</template>

<script>
export default {
  inheritAttrs: false,
  props: {
    active: Boolean,
    name: { type: String, default: 'fade' },
    delay: { type: Number, default: 0 }
  },
  data () {
    return {
      shown: this.active,
      timeout: null
    }
  },
  watch: {
    active (active) {
      if (!this.delay) {
        this.shown = active
      } else {
        if (this.timeout) {
          clearTimeout(this.timeout)
          this.timeout = null
        }

        this.timeout = setTimeout(() => {
          this.shown = this.active
          this.timeout = null
        }, this.delay)
      }
    }
  }
}
</script>

<style lang="scss">
// Slide down
.slide-down {
  &-enter-active,
  &-leave-active {
    transition: transform 0.5s ease-out;
  }
  &-enter,
  &-leave-to {
    transform: translateY(100%);
  }
}

// Zoom center
.zoom-center {
  &-enter-active,
  &-leave-active {
    transition: transform 0.5s ease-out;
  }
  &-enter,
  &-leave-to {
    transform-origin: center center;
    transform: scale(0);
  }
}

// Fade
.fade-enter {
  // display: no;
  opacity: 0;
}
.fade-enter-active {
  transition: opacity 0.5s ease;
}
.fade-leave {
  //   display: none;
}
.fade-leave-active {
  transition: opacity 0.5s ease;
  opacity: 0;
}

.zoom-out-enter-active,
.zoom-out-leave-active {
  transition: transform 1s ease;
}

.zoom-out-enter,
.zoom-out-leave-to {
  transform: translateX(100%);
  transition: all 0.9s ease-in 0s;
}
.zoom-in-enter-active,
.zoom-in-leave-active {
  transition: transform 1s ease;
}

.zoom-in-enter,
.zoom-in-leave-to {
  transform: translateX(-100%);
  transition: all 0.9s ease-in 0s;
}

.slide-enter-active,
.slide-leave-active {
  transition: width 1s, transform 0.2s ease;
  //   transform: translateX(0);
}
.slide-enter,
.slide-leave-to {
  width: 0;
  //   transform: translateX(-100%);
  //   transition: all 150ms ease-in 0s;
}
</style>
