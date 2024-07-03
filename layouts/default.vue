<template>
  <NLayout>
    <BlogHeader></BlogHeader>
    <NLayout :native-scrollbar="false" class="inner-layout" >
      <NLayoutContent content-style="padding: 24px;">
        <slot />
      </NLayoutContent>
      <BlogFooter>圆明园</BlogFooter>
    </NLayout>
  </NLayout>
</template>

<style>
.n-layout {
  height: 100%
}
.inner-layout {
  position: relative;
  top: 64px;
  height: calc(100vh - 64px)
}
.n-layout-content {
  min-height: calc(100vh - 64px)
}
</style>