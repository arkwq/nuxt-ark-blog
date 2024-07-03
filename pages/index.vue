<template>
  <NLayout class="index-container">
    <BlogSlideBanner :title="bannerInfo.title" :slogan="bannerInfo.slogan" />
  </NLayout>
</template>

<script setup lang="ts">
const bannerInfo = {
  title: 'Ark Blog',
  slogan: '人们总说时间会改变一切，但实际上你得自己来。'
}
</script>

<style scoped lang="scss">
.index-container {
  margin: 10px auto;
  position: relative;
  width: 1000px;
}
</style>
