<template>
  <div class="h-screen">
    <base-top-bar />
    <div class="flex main">
      <base-side-bar />
      <div class="w-full">
        <div class="main__divider" />
        <div class="flex h-full">
          <org-main-container>
            <template #title>
              <p>Task</p>
            </template>
            <template #image>
              <div>
                <base-icon name="add" size="30" />
                <p
                  class="text-sm mt-1"
                  style="color: #828282; line-height: 13px; font-size: 10px"
                >
                  Assign <br>
                  Agent
                </p>
              </div>
            </template>
            <template #content>
              <p>12b Emmanuel Hign street, Sur...</p>
              <p>
                <base-icon name="building" /> <span>Sterling Bank PLC</span>
              </p>
              <p style="color: #3056d3">
                a day ago
              </p>
            </template>
          </org-main-container>
          <div class="md:w-1/3 background" />
          <org-main-container class="main__content">
            <template #title>
              <p>Agents</p>
              <base-icon name="search" class="text-white mr-3" />
            </template>
            <template #image>
              <img
                class="w-8 h-8 rounded-full"
                src="@/assets/images/solomon.png"
                width="65"
                height="49"
                alt="User"
              >
            </template>
            <template #content>
              <p>08069786754</p>
              <p>Akure</p>
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
  &__divider {
    height: 40px;
    background: #fdfdfd;
  }
  .background {
    background-size: cover;
    background: url("~@/assets/images/map.png");
  }
}
</style>
