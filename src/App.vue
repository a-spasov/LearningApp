<template>
  <div class="container">
    <router-view/>  
    <footer>
      <nav>
      <hr>
        <router-link class="navItem" to="/">Home</router-link>
        <router-link class="navItem" to="/learning">Learning</router-link>
      </nav>
    </footer>
  </div>
</template>

<style>
  @import url('https://fonts.googleapis.com/css2?family=New+Tegomin&display=swap');

  .container {
    width: 80%;
    margin: auto;
    text-align: center;
  }
  footer {
    position: fixed;
    bottom: 0;
    width: 80%;
    font-weight: 700;
    font-family: 'New Tegomin', serif;
    font-size: 20px;
    background-color: white;
  }
  .navItem {
    margin: 10px 40px;
    text-decoration: none;
    float: left;
  }
  hr {
  clear: both;
  border: 0;
  height: 4px;
  background-image: linear-gradient(to right,rgba(0,0,0,0),rgba(0,0,0,.75),rgba(0,0,0,0));
  }
</style>
