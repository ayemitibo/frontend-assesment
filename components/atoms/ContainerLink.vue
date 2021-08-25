<template>
  <li
    class="
      container__link
      hover:bg-gray-100
      transition-all
      duration-75
      cursor-pointer
    "
  >
    <div class="w-full py-4 px-5">
      <div class="flex justify-between">
        <slot name="image" />
        <div class="container__link__content">
          <p>Abiodun Olawale Solomon</p>
          <div class="container__link__sub_content">
            <slot name="content" />
          </div>
        </div>
        <base-icon name="next" />
      </div>
    </div>
  </li>
</template>
<style lang="scss" scoped>
.container__link {
  border-bottom: 1px solid #f1f1f1;
  @apply py-3;
  &__content {
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    text-transform: capitalize;
    color: #000000;
    @apply flex-auto pl-3;
  }
  &__sub_content {
    p {
      color: #acb6be;
    }
  }
}
</style>
