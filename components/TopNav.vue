<template>
  <div class="center examplex">
    <vs-navbar center-collapsed v-model="active" shadow-scroll fixed>
      <template #left>
        <img src="/favicon.ico" alt="" width="30px" height="30px" />
      </template>
      <vs-navbar-item :active="active == 'guide'" id="guide" to="/">
        Home
      </vs-navbar-item>
      <vs-navbar-item :active="active == 'docs'" id="docs" to="/about">
        About
      </vs-navbar-item>
      <vs-navbar-item :active="active == 'contact'" id="contact" to="/contact">
        Contact
      </vs-navbar-item>
      <template #right>
        <vs-switch warn v-model="active2" @click="ChangeTheme">
          <template #circle>
            <i v-if="!active2" class="bx bxs-moon"></i>
            <i v-else class="bx bxs-sun"></i>
          </template>
        </vs-switch>
      </template>
    </vs-navbar>
  </div>
</template>

<script>
export default {
  data: () => ({
    active: "guide",
    active2: false,
  }),
  methods: {
    ChangeTheme() {
      const returnTheme = this.$vs.toggleTheme();
      this.$vsTheme = returnTheme == "dark";
      if (returnTheme == "dark") {
        document.body.classList.add("darken");
      } else {
        document.body.classList.remove("darken");
      }
    },
  },
};
</script>