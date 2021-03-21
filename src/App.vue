<template>
  <div id="app">
    <img src="cover.jpeg" width =100% height=300px alt="Bookshelf and Globe Selective Color - Union School by Photomatt28 is licensed with CC BY-NC-ND 2.0. To view a copy of this license, visit https://creativecommons.org/licenses/by-nc-nd/2.0/" />
    <div class ="header">
      <h1>Library Tracker</h1>
    </div>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>

    <div class = "footer">
      <hr>
      <p>My Github for this assignment can be found <a href="https://github.com/FlareDragoon/cp3">here</a></p>
    </div>
    
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  text-align: center;
  padding: 30px;
}

.footer {
  text-align: center;
  background-color: #5e75f2;
  color: white;
}

.footer a{
  color: white;
}

.header {
  text-align: center;
  background-color: #5e75f2;
  color: white;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #0f1cab;
}
</style>
