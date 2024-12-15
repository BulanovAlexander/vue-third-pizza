<script setup lang="ts">
import DefaultHeader from "./DefaultHeader.vue";
</script>

<template>
  <div class="app_layout">
    <DefaultHeader />
    <slot />
  </div>
</template>

<style lang="scss" scoped>
.default-layout {
  height: 100%;
  display: flex;
  flex-direction: column;
  flex: 1;
}
</style>
