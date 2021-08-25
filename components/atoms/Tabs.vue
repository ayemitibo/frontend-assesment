<template>
  <div>
    <!-- Tabs -->
    <ul class="grid grid-cols-3 w-full px-1 pt-2">
      <slot />
    </ul>
  </div>
</template>
<style lang="scss" scoped>
ul {
  border-bottom: 1px solid #f1f1f1;

  li {
    font-family: BR Sonoma;
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 18px;
    text-transform: capitalize;
    color: #c4c4c4;
  }

  & li.active {
    border-bottom: 1px solid #023a59;
    color: #023a59;
  }
}
</style>
