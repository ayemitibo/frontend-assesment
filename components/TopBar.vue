<template>
  <div class="flex w-full h-24">
    <div class="bg-white py-5">
      <a
        class="mx-7 text-lg font-bold text-gray-800 dark:text-gray-200"
        href="#"
      >
        <base-icon name="logo" style="width: auto; height: auto" />
      </a>
    </div>
    <header class="z-10 py-4 flex-auto flex items-center justify-between">
      <div class="btn-rounded w-8 h-8 flex justify-center items-center">
        <base-icon name="back" />
      </div>
      <div
        class="container flex items-center justify-between h-full px-6 mx-auto"
      >
        <!-- Search input -->
        <mol-search />
        <atom-notification />
        <div class="relative inline-flex">
          <button
            class="inline-flex justify-center items-center group"
            aria-haspopup="true"
            aria-expanded="false"
            style="outline: none"
          >
            <img
              class="w-8 h-8 rounded-full"
              src="@/assets/images/solomon.png"
              width="65"
              height="49"
              alt="User"
            >
            <div class="flex items-center truncate">
              <span
                class="
                  truncate
                  ml-2
                  text-sm
                  font-medium
                  group-hover:text-gray-800
                "
              >Solomon</span><svg
                class="w-3 h-3 flex-shrink-0 ml-1 fill-current text-gray-400"
                viewBox="0 0 12 12"
              >
                <path d="M5.9 11.4L.5 6l1.4-1.4 4 4 4-4L11.3 6z" />
              </svg>
            </div>
          </button>
          <div
            class="
              origin-top-right
              z-10
              absolute
              top-full
              right-0
              min-w-44
              bg-white
              border border-gray-200
              py-1.5
              rounded
              shadow-lg
              overflow-hidden
              mt-1
              exit-done
            "
            style="display: none"
          >
            <div>
              <div class="pt-0.5 pb-2 px-3 mb-1 border-b border-gray-200">
                <div class="font-medium text-gray-800">
                  Acme Inc.
                </div>
                <div class="text-xs text-gray-500 italic">
                  Administrator
                </div>
              </div>
              <ul>
                <li>
                  <a
                    class="
                      font-medium
                      text-sm text-indigo-500
                      hover:text-indigo-600
                      flex
                      items-center
                      py-1
                      px-3
                    "
                    href="/"
                    style="outline: none"
                  >Settings</a>
                </li>
                <li>
                  <a
                    class="
                      font-medium
                      text-sm text-indigo-500
                      hover:text-indigo-600
                      flex
                      items-center
                      py-1
                      px-3
                    "
                    href="/"
                    style="outline: none"
                  >Sign Out</a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </header>
  </div>
</template>
<style lang="scss" scoped>
.btn-rounded {
  box-shadow: 0px 2px 4px rgba(2, 58, 89, 0.16);
  border-radius: 50%;
  @apply bg-white;
}
</style>
