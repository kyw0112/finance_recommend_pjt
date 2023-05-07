<template>
  <div id="app" class="container">
    <!-- <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/deposit-list">정기예금목록</router-link>
    </nav> -->
    <b-navbar variant="success">
      <b-navbar-brand>
        <router-link to="/">Home</router-link>
      </b-navbar-brand>
      <b-navbar-nav>
        <b-nav-item>
          <router-link to="/about">About</router-link>
        </b-nav-item>
        <b-nav-item>
          <router-link to="/deposit-list">정기예금목록</router-link>
        </b-nav-item>
      </b-navbar-nav>
    </b-navbar>

    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* color: white; */
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  /* color: white; */
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
