<template>
  <div class="container">
    <atom-transition :name="transitionName" :active="iconShown">
      <div class="bg-white h-full">
        <div class="container__title">
          <slot name="title" />
        </div>
        <slot name="tab" :changeTab="changeTab" :activeTab="activeTab" />
        <atom-transition name="fade" active>
          <slot :activeTab="activeTab" />
        </atom-transition>
      </div>
    </atom-transition>
    <slot
      name="icon"
      :shown="() => (iconShown = !iconShown)"
      :isShown="iconShown"
    />
  </div>
</template>
<script>
export default {
  props: {
    transitionName: {
      type: String
    }
  },
  data () {
    return {
      activeTab: '',
      iconShown: true
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
  @apply h-full relative;

  .btn-paginate {
    width: 40px;
    height: 42px;
    background: #200e32;
    @apply flex justify-center items-center;
    color: white;

    &.right {
      right: calc(0px - 40px);
    }
    &.left {
      left: calc(0px - 40px);
    }
  }

  &__title {
    background: #46b2c8;
    font-family: BR Sonoma;
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    text-transform: capitalize;
    color: #ffffff;
    line-height: 21px;
    @apply flex items-center pl-3 justify-between py-2.5;
  }
}
</style>
