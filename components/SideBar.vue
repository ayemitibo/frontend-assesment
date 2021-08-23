<template>
  <aside
    class="
      z-20
      hidden
      w-56
      overflow-y-auto
      dark:bg-gray-800
      md:block
      flex-shrink-0
      bg-bg-color
    "
  >
    <div class="text-gray-500 dark:text-gray-400">
      <div class="text-white">
        <div style="background-color: #1c697a" class="flex justify-center p-5">
          <div>
            <p>Cheta And Daughters Limited</p>
            <span> RC123456789 </span>
          </div>
        </div>
        <ul class="pt-2 nav-group">
          <template v-for="(item, index) in navList">
            <atom-side-bar-list :key="index" :content="item" />
          </template>
        </ul>
      </div>
    </div>
  </aside>
</template>
<script>
export default {
  data () {
    return {
      navList: [
        {
          title: 'Dashboard',
          icon: 'dashboard'
        },
        {
          title: 'Agents',
          icon: 'agents'
        },
        {
          title: 'Task',
          icon: 'task'
        },
        {
          title: 'Teams',
          icon: 'teams'
        },
        {
          title: 'Users',
          icon: 'users'
        },
        {
          title: 'Settings',
          icon: 'settings'
        }
      ]
    }
  }
}
</script>
<style lang="scss">
ul {
  span {
    font-style: normal;
    font-weight: 500;
    font-size: 18px;
    line-height: 23px;
    color: #c2e2e9;
  }

  & li:first-child {
    background: #46b2c8;
    span {
      color: #ffffff;
    }
  }
}
</style>
