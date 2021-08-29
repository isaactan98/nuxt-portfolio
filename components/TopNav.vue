<template>
  <div class="center examplex">
    <vs-navbar center-collapsed v-model="active">
      <template #left>
        <img src="/" alt="" />
      </template>
      <vs-navbar-item :active="active == 'guide'" id="guide" to="/">
        Home
      </vs-navbar-item>
      <vs-navbar-item :active="active == 'docs'" id="docs" to="/about">
        About
      </vs-navbar-item>
      <vs-navbar-item :active="active == 'components'" id="components">
        Components
      </vs-navbar-item>
      <vs-navbar-item :active="active == 'license'" id="license">
        license
      </vs-navbar-item>
      <template #right>
        <vs-switch color="warning" v-model="active2" @click="ChangeTheme">
          <template #circle>
            <i v-if="!active2" class="bx bxs-sun"></i>
            <i v-else class="bx bxs-moon"></i>
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
      if (returnTheme == "dark" && this.active2 != true) {
        document.body.classList.add("darken");
      } else {
        document.body.classList.remove("darken");
      }
    },
  },
};
</script>