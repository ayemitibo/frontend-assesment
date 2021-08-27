<template>
  <ul class="bg-white h-full-container overflow-y-auto">
    <atom-container-link v-for="item in 7" :key="item">
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
        <p class="py-1">
          12b Emmanuel Hign street, Sur...
        </p>
        <p>
          <base-icon name="building" size="18" /> <span>Sterling Bank PLC</span>
        </p>
        <p style="color: #3056d3" class="pt-3">
          a day ago
        </p>
      </template>
    </atom-container-link>
  </ul>
</template>
