<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Главная</router-link> |
      <router-link to="/about">Рецепты</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');
  #app {
    margin: 0;
    padding: 0;
    font-family: 'Roboto', sans-serif;
    color: #222;
    text-align: center;
  }

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
