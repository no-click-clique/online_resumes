<template>
  <div id="app">
    <div id="nav">
     <!--  <router-link to="/students/1">Students Resume</router-link> | -->
      <router-link to="/">Home</router-link>
      |
      <router-link to="/about">About</router-link>
      |
      <router-link to="/students">Students Index</router-link>
    </div>
    <router-view />
  </div>
</template>

<style>
  img {
    width: 200px;
  }
</style>
