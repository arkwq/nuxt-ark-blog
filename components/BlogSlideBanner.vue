<template>
  <div class="slide-banner">
    <div class="bg"></div>
    <div class="slide-banner-a"></div>
    <div class="slide-banner-b"></div>
    <div class="slide-banner-d"></div>
    <div class="slide-banner-c"></div>
    <div>
      <h1 class="title">{{ title }}</h1>
      <p class="slogan">{{ slogan }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  title: string
  slogan: string
}>()
</script>

<style scoped lang="scss">
.slide-banner {
  position: relative;
  width: 100%;
  height: 400px;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  border-radius: 5px;
}

.bg{
  background-image: url("~/assets/imgs/ark.jpg");
  background-size: cover;
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  transition: 0.8s;
}

.slide-banner-a,
.slide-banner-b,
.slide-banner-c,
.slide-banner-d {
  position: absolute;
  width: 100%;
  height: 400px;
  background-size: cover;
  display: flex;
  justify-content: center;
  overflow: hidden;
  opacity: 0.5;
  transition: 0.6s;
}

.slide-banner-a::after,
.slide-banner-b::after,
.slide-banner-c::after,
.slide-banner-d::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 400px;
  background-image: url("~/assets/imgs/ark.jpg");
  background-size: cover;
}

.slide-banner-a {
  left: -400px;
  transform: rotateZ(100deg);
  filter: drop-shadow(4px 4px 12px rgba(0, 0, 0, 1));
}

.slide-banner-a::after {
  transform: rotateZ(-100deg);
  background-position-x: 400px;
}

.slide-banner-b {
  left: -400px;
  transform: rotateZ(-100deg);
  filter: drop-shadow(4px 4px 12px rgba(0, 0, 0, 1));
  transition-delay: 0.2s;
}

.slide-banner-b::after {
  transform: rotateZ(100deg);
  background-position-x: 400px;
}

.slide-banner-c {
  right: -400px;
  transform: rotateZ(100deg);
  filter: drop-shadow(4px 4px 12px rgba(0, 0, 0, 1));
  transition-delay: 0.2s;
}

.slide-banner-c::after {
  transform: rotateZ(-100deg);
  background-position-x: -400px;
}

.slide-banner-d {
  right: -400px;
  transform: rotateZ(-100deg);
  filter: drop-shadow(4px -4px 12px rgba(0, 0, 0, 1));
}

.slide-banner-d::after {
  transform: rotateZ(100deg);
  background-position-x: -400px;
}

.title {
  position: relative;
  font: 400 40px "";
  margin-block-start: 1em;
  margin-block-end: 1em;
  user-select: none;
  color: white;
  text-align: center;
}

.slogan {
  opacity: 0;
  filter: blur(15px);
  font: 200 22px "";
  user-select: none;
  color: white;
  transition: 0.3s;
}

.slide-banner:hover .bg {
  filter: brightness(0.5);
}

.slide-banner:hover .slide-banner-a,
.slide-banner:hover .slide-banner-b {
  left: -600px;
  opacity: 0;
}

.slide-banner:hover .slide-banner-c,
.slide-banner:hover .slide-banner-d {
  right: -600px;
  opacity: 0;
}

.slide-banner:hover .slogan {
  opacity: 1;
  filter: blur(0);
  transition-delay: 0.3s;
}
</style>