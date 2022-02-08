<template>
  <div id="app">
    <div id="nav">
      <router-link to="/vuedraggable">vuedraggable拖拽</router-link> |
      <router-link to="/turntable">turntable大转盘</router-link>
    </div>
        <router-view />

  </div>
</template>

<style lang="less">
* {
  margin: 0;
  padding: 0;
}
html,
body {
  width: 100%;
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  #nav {
    padding: 15px;

    a {
      font-weight: bold;
      color: #2c3e50;

      &.router-link-exact-active {
        color: #42b983;
      }
    }
    router-view {
      flex: 1;
      width: 100%;
      background: green;
    }
  }
}
</style>
