<template>
  <ul>
    <atom-container-link>
      <template #image>
        <slot name="image" />
      </template>
      <template #content>
        <slot name="content" />
      </template>
    </atom-container-link>
  </ul>
</template>
