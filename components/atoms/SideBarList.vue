<template>
  <li class="relative px-6 py-3 my-5">
    <a
      class="
        inline-flex
        items-center
        w-full
        text-sm
        font-semibold
        transition-colors
        duration-150
        hover:text-gray-800
        dark:hover:text-gray-200
      "
      href="#"
    >
      <base-icon :name="content.icon" size="20" />
      <span class="ml-4" :style="{ color: content.color }">{{
        content.title
      }}</span>
    </a>
  </li>
</template>
<script>
export default {
  props: {
    content: {
      type: Object,
      required: true,
      default: () => {}
    }
  }
}
</script>
<style lang="scss" scoped>
span {
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 23px;
  color: #c2e2e9;
}
</style>
