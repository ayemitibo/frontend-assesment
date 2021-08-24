<template>
  <div>
    <!-- Tabs -->
    <ul class="inline-flex w-full px-1 pt-2">
      <li class="px-4 py-2 -mb-px">
        <a id="default-tab" href="#first">24 Unassigned</a>
      </li>
      <li class="px-4 py-2 font-semibold">
        <a href="#second">12 assigned</a>
      </li>
      <li class="px-4 py-2 font-semibold">
        <a href="#third">30 Completed</a>
      </li>
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

  & li:first-child {
    border-bottom: 1px solid #023a59;
    color: #023a59;
  }
}
</style>
