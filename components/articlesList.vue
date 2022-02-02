<template>
  <div>
    <div class="container">
      <div v-for="NewsData in NewsDataList" :key="NewsData.id" class="news-wrapper" >
        <div class="news-img">
          <img :src="'/images/' + NewsData.preview_image">
        </div>

        <div class="desc_articles_wrapper">
          <div class="articles-name">
            <h2>{{NewsData.name}}</h2>
          </div>
          <div class="news-date">
            <span>{{NewsData.date}}</span>
          </div>
          <div class="news-shortDesc">{{NewsData.shortDesc}}</div>
        </div>

        <button class="btn btn_articles">
          <NuxtLink :to="{name:'articles-id' , params: { id: NewsData.id}}">Подробнее</NuxtLink>
        </button>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  layout: 'header',
  data () {
    return {
      NewsDataList: [],
    }
  },
  async fetch() {
    this.NewsDataList = await fetch(
      'http://demo-api.vsdev.space/api/articles'
    ).then(res => res.json())
    console.log(this.NewsDataList)
  }
}
</script>

<style>
.desc_articles_wrapper {
  padding: 0 30px 30px 30px;
}

.container{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  max-width: 1300px;
  justify-content: space-between;
}
.news-wrapper {
  position: relative;
  margin-bottom: 50px;
  width: 410px;
  height: 530px;
  background-color: #ffffff;
  border-radius: 20px;
  border-color: #ea00ff;
}

.news-shortDesc {
  margin-top: 15px;
  font-size: 20px;
}
.articles-name{
  font-size: 20px;
  margin: 20px 0 5px 0;
}

.news-img img{
  width: 100%;
  height: 270px;
  border-radius: 20px 20px 0 0;
}
.btn_articles {
  padding: 10px 55px;
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
}
</style>
