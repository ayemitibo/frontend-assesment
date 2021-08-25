<template>
  <div class="h-screen">
    <base-top-bar />
    <div class="flex main">
      <base-side-bar />
      <div class="w-full">
        <div class="main__divider" />
        <div class="flex main__page_content">
          <!-- Task -->
          <org-main-container>
            <template #tab="{ changeTab, activeTab }">
              <atom-tabs>
                <li
                  class="py-2 -mb-px"
                  :class="[
                    activeTab == 'unassigned' || activeTab == ''
                      ? 'active'
                      : '',
                  ]"
                  @click="changeTab('unassigned')"
                >
                  <a id="default-tab" href="#">24 Unassigned</a>
                </li>
                <li
                  class="px-4 py-2 font-semibold"
                  :class="[activeTab == 'assigned' ? 'active' : '']"
                  @click="changeTab('assigned')"
                >
                  <a href="#">12 assigned</a>
                </li>
                <li
                  class="py-2 font-semibold"
                  :class="[activeTab == 'completed' ? 'active' : '']"
                  @click="changeTab('completed')"
                >
                  <a href="#">30 Completed</a>
                </li>
              </atom-tabs>
            </template>
            <template #title>
              <p>Task</p>
            </template>
            <template #default="{ activeTab }">
              <mol-un-assign-task
                v-if="activeTab == 'unassigned' || activeTab == ''"
              />
              <mol-assign-task v-if="activeTab == 'assigned' ? 'active' : ''" />
              <mol-completed-task
                v-if="activeTab == 'completed' ? 'active' : ''"
              />
            </template>
          </org-main-container>

          <!-- Image -->
          <div
            class="md:w-2/5 relative background"
            style="background-size: cover; background-position: center"
          >
            <div class="btn-paginate absolute top-0 left-0">
              <base-icon name="next" :rotate="-180" />
            </div>
            <div class="btn-paginate absolute top-0 right-0">
              <base-icon name="next" />
            </div>
          </div>

          <!-- Agents -->
          <org-main-container class="main__content">
            <template #tab="{ changeTab, activeTab }">
              <atom-tabs>
                <li
                  class="px-4 py-2 -mb-px"
                  :class="[
                    activeTab == 'all' || activeTab == '' ? 'active' : '',
                  ]"
                  @click="changeTab('all')"
                >
                  <a id="default-tab" href="#">All</a>
                </li>
                <li
                  class="flex items-center px-4 py-2 font-semibold"
                  :class="[activeTab == 'online' ? 'active' : '']"
                  @click="changeTab('online')"
                >
                  <div class="rounded_div" style="background-color: #2eb255" />
                  <a href="#">Online</a>
                </li>
                <li
                  class="flex items-center px-4 py-2 font-semibold"
                  :class="[activeTab == 'offline' ? 'active' : '']"
                  @click="changeTab('offline')"
                >
                  <div class="rounded_div" style="background-color: #d14349" />
                  <a href="#">Offline</a>
                </li>
              </atom-tabs>
            </template>
            <template #title>
              <p>Agents</p>
              <base-icon name="search" class="text-white mr-3" />
            </template>
            <template #default="{ activeTab }">
              <mol-all-agents v-if="activeTab == 'all' || activeTab == ''" />
              <mol-online-agents v-if="activeTab == 'online'" />
              <mol-offline-agents v-if="activeTab == 'offline'" />
            </template>
          </org-main-container>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>
<style lang="scss" scoped>
.main {
  min-height: calc(100vh - 6rem);
  &__divider {
    height: 40px;
    background: #fdfdfd;
    border-top: 2px solid #f1f1f1;
  }

  &__page_content {
    min-height: calc(100% - 40px);

    .rounded_div {
      width: 10px;
      height: 10px;
      @apply mr-2 rounded-full;
    }

    .btn-paginate {
      width: 40px;
      height: 42px;
      background: #200e32;
      @apply flex justify-center items-center;
      color: white;
    }
  }
  .background {
    background: url("~@/assets/images/map.png");
  }
}
</style>
