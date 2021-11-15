<template>
  <nav class="app-nav">
    <router-link to="/login" class="app-nav-link">Авторизация</router-link>
    <router-link to="/" class="app-nav-link">Главная</router-link>
    <router-link to="/showcase" class="app-nav-link">Магазин</router-link>
  </nav>

  <main class="app-main">
    <router-view/>
  </main>
</template>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  min-width: 320px;
  padding: 0 3%;
}


.app-nav,
.app-main {
  max-width: 960px;
  margin: 0 auto;
}
.app-main {
  padding: 40px 0;
}
.app-nav {
  display: flex;
  justify-content: flex-end;
  height: 60px;
  line-height: 62px;
}


.app-nav-link {
  font-weight: bold;
  padding: 0 8px;
}
.app-nav-link.router-link-exact-active {
  border-bottom: 2px solid dodgerblue;
}

</style>
