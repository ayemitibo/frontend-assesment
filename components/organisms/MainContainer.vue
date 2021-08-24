<template>
  <div class="md:w-1/3 container">
    <div class="container__title">
      <slot name="title" />
    </div>
    <atom-tabs />
    <mol-container-list>
      <template #image>
        <slot name="image" />
      </template>
      <template #content>
        <slot name="content" />
      </template>
    </mol-container-list>
  </div>
</template>
<style lang="scss" scoped>
.container {
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
</style>
