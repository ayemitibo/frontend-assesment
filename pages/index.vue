<template>
  <div class="h-screen">
    <base-top-bar :is-opened="isOpened" @isOpen="isOpened = !isOpened" />
    <div class="flex main">
      <atom-transition :name="'slide'" :active="isOpened">
        <base-side-bar />
      </atom-transition>
      <div
        class="w-full"
        :class="[isOpened ? 'w-full transition-all duration-75' : '']"
      >
        <div class="main__divider" />
        <div class="relative main__page_content">
          <!-- Task -->
          <div class="absolute h-full left-0 w-30">
            <org-main-container :transition-name="'zoom-in'">
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
                <mol-assign-task
                  v-if="activeTab == 'assigned' ? 'active' : ''"
                />
                <mol-completed-task
                  v-if="activeTab == 'completed' ? 'active' : ''"
                />
              </template>
              <template #icon="{ shown, isShown }">
                <div
                  class="btn-paginate absolute top-0 cursor-pointer right"
                  @click="shown()"
                >
                  <base-icon name="next" :rotate="isShown ? '-180' : ''" />
                </div>
              </template>
            </org-main-container>
          </div>

          <!-- Agents -->
          <div class="absolute h-full right-0 w-30">
            <org-main-container :transition-name="'zoom-out'">
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
                    <div
                      class="rounded_div"
                      style="background-color: #2eb255"
                    />
                    <a href="#">Online</a>
                  </li>
                  <li
                    class="flex items-center px-4 py-2 font-semibold"
                    :class="[activeTab == 'offline' ? 'active' : '']"
                    @click="changeTab('offline')"
                  >
                    <div
                      class="rounded_div"
                      style="background-color: #d14349"
                    />
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
              <template #icon="{ shown, isShown }">
                <div
                  class="btn-paginate absolute top-0 cursor-pointer left"
                  @click="shown()"
                >
                  <base-icon name="next" :rotate="isShown ? '' : '-180'" />
                </div>
              </template>
            </org-main-container>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isOpened: true,
      isAgentShown: true,
      isTaskShown: true
    }
  }
}
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
    height: calc(100% - 40px);
    background: url("~@/assets/images/map.png");

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
}
</style>
