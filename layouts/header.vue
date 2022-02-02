<template>
  <div>
    <nav>
      <div class="header">
        <div class="navinfo">
          <router-link to="/" class="logo"><img src="../assets/news.png" alt="logo"></router-link>
          <div class="nav">
            <NuxtLink to="/">Главная </NuxtLink> 
            <NuxtLink to="/articles">Новости</NuxtLink>  
            <NuxtLink to="/galery">Галерея </NuxtLink>
          </div>
        </div>
        <form class="search__form ">
          <v-text-field
            class="theme--dark theme--light"
            color="white"
          ></v-text-field>
          <button >Поиск</button>
        </form>
      </div>
    </nav>
    <Nuxt></Nuxt>
  </div>

</template>

<style>
nav {
  background-color: #a300a3;
  color: #ffff;
}
img {
  height: 30px;
}

.navinfo {
  margin-left: 50px;
  width: 100%;
  display: flex;
  align-content: center;
  align-items: center;
}
.nav {
  margin: 30px;
  font-size: 20px;
  display: flex;
  justify-content: space-between;
  
  
}

.nav a.nuxt-link-exact-active, .nav a:hover {
  color: rgb(62, 0, 68);
  font-weight: bold;
}
.nav a {
  margin-left: 50px;
  text-decoration: none;
  color: #fff;

}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 1300px;
  margin: 0 auto;
}

.search__form {
  display: flex;
  align-items: center;
  justify-content: space-around;
}


</style>
