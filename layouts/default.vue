<template>
  <div>
    <top-nav />
    <Nuxt id="padding-scroll-content" />
  </div>
</template>

<script>
import Vue from "vue";
import Vuesax from "vuesax";

import "vuesax/dist/vuesax.css"; //Vuesax styles
Vue.use(Vuesax, {
  // options here
});
import "material-icons/iconfont/material-icons.css";

import TopNav from "~/components/TopNav.vue";
export default {
  head() {
    return {
      link: [
        {
          rel: "stylesheet",
          href: "https://vuesax.com/assets/css/0.styles.9c3c9a79.css",
        },
      ],
    };
  },
  components: {
    TopNav,
  },
  data: () => ({
    active: "docs",
  }),
};
</script>

<style>
body{
  overflow-y: auto;
}
.darken {
  background: #1e2023;
}
.vh-95{
  min-height: 100vh;
  width: 100%;
}
</style>