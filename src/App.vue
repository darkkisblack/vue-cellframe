<template>
  <div id="app">
    <router-view />
  </div>
</template>
<style lang="scss">
#app {
  display: flex;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: var(--main-b-gcolor, #2e3138);
  /* width: 1280px;
  height: 720px; */
  width: 100%;
  height: 100%;
}

body {
  margin: 0;
}
</style>
