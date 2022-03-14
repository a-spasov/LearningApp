<template>
    <h1>{{ msg }}</h1>
    <img v-if="isLogged == 'true'" alt="Logo picture" src='../assets/profileIcon.png'>
    <hr>
</template>

<script>
export default {
  name: "PageHeader",
  props: {
    msg: String,
    isLogged: Boolean,
  },
};
</script>

<style scope>
@import url('https://fonts.googleapis.com/css2?family=New+Tegomin&display=swap');

h1 {
  font-weight: 600;
  font-family: 'New Tegomin', serif;
  font-size: 64px;
  display: inline;
  margin: auto;
}
hr {
  clear: both;
  border: 0;
  height: 2px;
  background-image: linear-gradient(to right,rgba(0,0,0,0),rgba(0,0,0,.75),rgba(0,0,0,0));
}
img {
  width: 85px;
  display: inline-block;
  float: right;
  vertical-align: middle;
}

</style>