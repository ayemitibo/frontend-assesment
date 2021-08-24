<template>
  <div class="w-full search__input">
    <div
      class="p-1 flex border border-gray-200 rounded search__input__container"
    >
      <div
        class="
          text-gray-300
          w-20
          py-1
          pl-2
          pr-1
          border-r
          flex
          items-center
          justify-between
          border-gray-200
        "
      >
        <p>All</p>
        <button
          class="
            cursor-pointer
            w-6
            h-6
            text-gray-600
            outline-none
            justify-between
            focus:outline-none
          "
        >
          <base-icon name="down" size="10" />
        </button>
      </div>
      <input
        class="p-1 px-2 outline-none w-full text-gray-800"
        placeholder="Search for anything here"
      />
      <div class="flex items-center mr-2">
        <base-icon name="search" />
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.search__input {
  font-family: Euclid Circular A Trial;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 18px;
  color: #999999;
  width: 890px;
  @apply h-full;
  input {
    background: transparent;
  }

  &__container {
    background: #f1f1f1;
    border: 2px solid #ffffff;
    @apply h-full;
  }
}
</style>
