<template>
  <div>
    <h1 class="articles_title">Новости</h1>
    <div class="wrapper">
      <img src="/images/full.jpeg" alt="" class="galery_img">
      <img src="/images/full_2.jpeg" alt="" class="galery_img">
      <img src="/images/preview_2.jpg" alt="" class="galery_img">
      <img src="/images/preview.jpg" alt="" class="galery_img">
      <img src="/images/preview.jpg" alt="" class="galery_img">
      <img src="/images/preview.jpg" alt="" class="galery_img">
      <img src="/images/full_2.jpeg" alt="" class="galery_img">
      <img src="/images/preview_2.jpg" alt="" class="galery_img">
    </div>
  </div>
</template>

<script>
export default {
  layout: 'header',
}
</script>

<style>
.wrapper {
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex-wrap: wrap;
  margin: 50px 100px 50px 100px;
}

.galery_img {
  margin-top: 30px;
  width: 400px;
  height: 270px;
}
</style>
