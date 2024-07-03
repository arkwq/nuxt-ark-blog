<template>
  <NConfigProvider :theme="darkTheme" theme-overrides="themeOverrides">
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </NConfigProvider>
</template>

<script setup lang='ts'>
import { darkTheme, type GlobalThemeOverrides } from 'naive-ui'
const themeOverrides: GlobalThemeOverrides = {
  common: {
    primaryColor: '#8A2BE2'
  }
}
</script>

<style>
html,body, #__nuxt, #__layout {
  height:100%!important;
  width: 100%!important;
}
.n-config-provider {
  height: 100%
}
</style>
