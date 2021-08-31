<template>
  <div class="vh-95">
    <div class="center">
      <h2>Contact</h2>
    </div>
    <div class="center content-inputs">
      <vs-input
        shadow
        primary
        type="email"
        icon-after
        v-model="value3"
        label-placeholder="Email"
        size="large"
        id="email"
        readonly
      >
        <template #icon>
          <i class="bx bx-mail-send"></i>
        </template>
      </vs-input>
      <vs-button ref="button" flat @click="handleClick">
        <b>Copy</b>
      </vs-button>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    active: "contact",
    value3: "iztan98@gmail.com",
  }),
  methods: {
    handleClick() {
      const loading = this.$vs.loading({
        target: this.$refs.button,
        scale: "0.6",
        background: "primary",
        opacity: 1,
        color: "#fff",
      });
      this.$copyText(this.value3);
      setTimeout(() => {
        loading.close();
      }, 3000);
    },
  },
};
</script>

<style>
</style>