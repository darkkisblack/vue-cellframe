<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style lang="scss">
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: var(--main-b-gcolor, #2e3138);
}

body {
  margin: 0;
}
</style>
