<template>
  <PageHeader msg="Welcome" isLogged = true />
  <div class="content">
    <ActionsForm />
  </div>
</template>

<script>
import PageHeader from "@/components/Header.vue";
import ActionsForm from "@/components/ActionsForm.vue";

export default {
  name: "HomeView",
  components: {
    PageHeader,
    ActionsForm
  },
};
</script>

<style scope>
@import url('https://fonts.googleapis.com/css2?family=New+Tegomin&display=swap');

h1 {
  font-weight: 600;
  font-family: 'New Tegomin', serif;
  font-size: 64px;
}
hr {
  clear: both;
  border: 0;
  height: 2px;
  background-image: linear-gradient(to right,rgba(0,0,0,0),rgba(0,0,0,.75),rgba(0,0,0,0));
}
.content {
    overflow: auto;
    margin-bottom: 100px;
}
</style>


