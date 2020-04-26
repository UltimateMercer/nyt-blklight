<template>
  <div id="app">
    <div class="container">
      <div class="nav-scroller py-1 my-3">
        <nav class="nav d-flex">
          <router-link to="/" class="marker marker-dark marker-link"
            >Home</router-link
          >
          <router-link to="/World" class="marker marker-dark marker-link">
            World
          </router-link>
        </nav>
      </div>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
@import "style/css/ultimate.min.css";
</style>
