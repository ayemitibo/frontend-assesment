<template>
  <ul>
    <atom-container-link v-for="item in 5" :key="item">
      <template #image>
        <img
          class="w-8 h-8 rounded-full"
          src="@/assets/images/2.png"
          width="65"
          height="49"
          alt="User"
        >
      </template>
      <template #content>
        <p>08069786754</p>
        <p>Akure</p>
      </template>
    </atom-container-link>
  </ul>
</template>
