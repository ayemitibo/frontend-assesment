<template>
  <div class="container">
    <div class="container__title">
      <slot name="title" />
    </div>
    <slot name="tab" :changeTab="changeTab" :activeTab="activeTab" />
    <transition name="fade" mode="out-in">
      <slot :activeTab="activeTab" />
    </transition>
  </div>
</template>
<script>
export default {
  data () {
    return {
      activeTab: ''
    }
  },
  methods: {
    changeTab (tab) {
      this.activeTab = tab
    }
  }
}
</script>
<style lang="scss" scoped>
.container {
  width: 30%;
  @apply h-full;
  &__title {
    height: 42px;
    background: #46b2c8;
    @apply flex items-center pl-3 justify-between;
    p {
      font-family: BR Sonoma;
      font-style: normal;
      font-weight: 600;
      font-size: 16px;
      text-transform: capitalize;
      color: #ffffff;
      line-height: 21px;
    }
  }
}

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
</style>
