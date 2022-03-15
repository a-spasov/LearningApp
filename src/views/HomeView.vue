<template>
  <PageHeader msg="Learning" isLogged = false />
  <div class="content">
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque elit tellus, convallis vel purus ut, ornare laoreet purus. Donec auctor commodo quam, vitae tincidunt magna finibus a. Pellentesque libero lectus, iaculis ut lorem dignissim, pretium finibus sem. Donec nec cursus elit. Pellentesque lorem purus, mollis sit amet hendrerit non, pretium sit amet nisi. Vivamus accumsan quis ipsum ut dignissim. Nulla faucibus dapibus maximus. Nullam consequat malesuada augue, quis lobortis ligula congue a. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin consectetur dictum libero, at venenatis libero. In lorem risus, ultrices vel ultricies et, auctor id sapien. Integer eu risus erat. Integer sollicitudin consequat ligula, vitae facilisis ligula ornare at. Morbi a auctor felis. Quisque sodales elit metus, eget vulputate libero maximus vitae.</p>
    <p>Quisque porta elit nisl, in commodo lectus vehicula molestie. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Nulla efficitur, ex sed ultrices malesuada, massa elit pretium nibh, eu ultrices diam leo vitae erat. Ut sed turpis eleifend, tempor est mattis, tincidunt mauris. Curabitur placerat leo leo, vitae pulvinar diam tempus et. Vivamus molestie libero mi, quis rutrum quam porttitor vel. Donec tincidunt urna in consectetur condimentum. Quisque sit amet eros dui. Nulla iaculis ultrices dolor vitae semper.</p>
    <p>Morbi interdum dui eget fringilla ultrices. Donec non justo at leo ullamcorper pellentesque ut eget quam. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Nunc ornare ante lobortis luctus pellentesque. Vestibulum sed urna ut dolor convallis interdum. Phasellus sit amet laoreet eros, quis dictum nisi. Curabitur auctor hendrerit cursus. Suspendisse mi neque, tristique in neque quis, egestas ullamcorper massa. In interdum sollicitudin accumsan.</p>
    <p>Nullam consequat malesuada augue, quis lobortis ligula congue a. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin consectetur dictum libero, at venenatis libero. In lorem risus, ultrices vel ultricies et, auctor id sapien. Integer eu risus erat. Integer sollicitudin consequat ligula, vitae facilisis ligula ornare at. Morbi a auctor felis. Quisque sodales elit metus, eget vulputate libero maximus vitae.</p>
  </div>
</template>

<script>
import PageHeader from "@/components/Header.vue";

export default {
  name: "HomeView",
  components: {
    PageHeader,
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
  margin-top: 30px;
}
</style>

