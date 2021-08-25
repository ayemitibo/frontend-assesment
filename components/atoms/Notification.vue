<template>
  <div class="notification__container">
    <span class="relative inline-block">
      <base-icon name="notification" />
      <span class="notification__container__number">2</span>
    </span>
  </div>
</template>
<style lang="scss" scoped>
.notification__container {
  background: rgba(194, 226, 233, 0.2);
  border-radius: 12px;
  width: 48px;
  height: 48px;
  @apply flex justify-center items-center mr-6;
  &__number {
    font-family: Euclid Circular A Trial;
    font-style: normal;
    font-weight: normal;
    font-size: 12.0909px;
    line-height: 15px;
    background: #d72830;
    width: 19px;
    height: 19px;
    @apply absolute top-0 right-0 inline-flex items-center justify-center px-2 py-1 transform translate-x-1/2  -translate-y-1/2 rounded-full text-white;
  }
}
</style>
