<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-dark py-lg-4" id="mainNav">
      <div class="container">
        <a class="navbar-brand text-uppercase text-expanded font-weight-bold d-lg-none" href="#">ACTUALIZE STUDENTS</a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarResponsive"
          aria-controls="navbarResponsive"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarResponsive">
          <ul class="navbar-nav mx-auto">
            <li class="nav-item active px-lg-4">
              <a class="nav-link text-uppercase text-expanded" href="/">
                Home
                <span class="sr-only">(current)</span>
              </a>
            </li>
            <li class="nav-item px-lg-4">
              <a class="nav-link text-uppercase text-expanded" href="/about">About</a>
            </li>
            <li class="nav-item px-lg-4">
              <a class="nav-link text-uppercase text-expanded" href="/students">Students</a>
            </li>
            <!-- <li class="nav-item px-lg-4">
              <a class="nav-link text-uppercase text-expanded" href="store.html">Store</a>
            </li> -->
          </ul>
        </div>
      </div>
    </nav>
    <!-- 
    <div id="nav">
      <router-link to="/">Home</router-link>
      |
      <router-link to="/about">About</router-link>
      |
      <router-link to="/students">Students Index</router-link>
    </div> -->

    <router-view />

    <footer class="footer text-faded text-center py-5">
      <div class="container">
        <p class="m-0 small">Copyright Ben and Mike Website 2020</p>
      </div>
    </footer>
  </div>
</template>

<style></style>
