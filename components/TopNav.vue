<template>
  <div class="center">
    <vs-navbar
      shadow-scroll
      fixed
      padding-scroll
      right-collapsed
      v-model="active"
    >
      <template #left>
        <vs-button
          @click="activeSidebar = !activeSidebar"
          icon
          shadow
          size="xl"
        >
          <i class="bx bx-menu"></i>
        </vs-button>
      </template>

      <vs-navbar-item :active="active == 'home'" id="home" to="/">
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
            <i v-if="active2" class="bx bxs-moon"></i>
            <i v-else class="bx bxs-sun"></i>
          </template>
        </vs-switch>
      </template>
    </vs-navbar>
    <!-- Side Bar -->
    <vs-sidebar absolute v-model="active" :open.sync="activeSidebar">
      <template #logo>
        <img src="/favicon.ico" alt="" />
      </template>
      <vs-sidebar-item id="home" to="/">
        <template #icon>
          <i class="bx bx-home"></i>
        </template>
        Home
      </vs-sidebar-item>
      <vs-sidebar-item id="docs" to="/about">
        <template #icon>
          <i class="bx bx-grid-alt"></i>
        </template>
        About
      </vs-sidebar-item>
      <vs-sidebar-item id="contact" to="/contact">
        <template #icon>
          <i class="bx bxs-music"></i>
        </template>
        Contact
      </vs-sidebar-item>
      <vs-sidebar-item id="chat">
        <template #icon>
          <i class="bx bx-chat"></i>
        </template>
        Chat
      </vs-sidebar-item>
      <template #footer>
        <vs-row justify="space-between">
          <vs-switch warn v-model="active2" @click="ChangeTheme">
            <template #circle>
              <i v-if="active2" class="bx bxs-moon"></i>
              <i v-else class="bx bxs-sun"></i>
            </template>
          </vs-switch>
        </vs-row>
      </template>
    </vs-sidebar>
  </div>
</template>

<script>
export default {
  data: () => ({
    active: "home",
    active2: false,
    activeSidebar: false,
  }),
  methods: {
    ChangeTheme() {
      const returnTheme = this.$vs.toggleTheme();
      this.storeToken(returnTheme);
      this.$vsTheme = returnTheme == "dark";
      if (returnTheme == "dark") {
        this.active2 = true;
        document.body.classList.add("darken");
      } else {
        this.active2 = false;
        document.body.classList.remove("darken");
      }
      console.log(this.active2);
    },
    storeToken(themeToken) {
      if (process.client) {
        localStorage.setItem("theme", themeToken);
      }
    },
  },
  mounted() {
    const getTheme = localStorage.getItem("theme");

    if (getTheme == "dark") {
      this.active2 = true;
      this.$vs.setTheme("dark");
      document.body.classList.add("darken");
    }
  },
};
</script>