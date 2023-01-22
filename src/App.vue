<template>
  <div id="app">
    <Header />
    <Body />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/header.vue";
import Footer from "./components/footer.vue";
import Body from "./components/body.vue";
export default {
  name: "App",
  components: {
    Header,
    Footer,
    Body,
  },
};
</script>


