<template>
  <div class="center vh-95">
    <div class="center"><h2>Contact</h2></div>
    <div class="center content-inputs">
      <vs-input
        shadow
        primary
        type="email"
        icon-after
        v-model="value3"
        label-placeholder="Email"
        id="email"
        readonly
      >
        <template #icon>
          <i class="bx bx-mail-send"></i>
        </template>
      </vs-input>
      <vs-button
        @click="handleClick"
        :icon="success"
        :upload="sending"
        :color="success ? 'success' : 'primary'"
      >
        <span v-if="!success">
          <i class="bx bx-mail-send"></i>
          Copy
        </span>

        <i class="bx bx-check" v-else></i>
      </vs-button>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    active: "contact",
    value3: "iztan98@gmail.com",
    sending: false,
    success: false,
  }),
  methods: {
    handleClick() {
      this.sending = true;
      this.$copyText(this.value3);
      setTimeout(() => {
        this.sending = false;
        this.success = !this.success;
      }, 1000);
    },
  },
};
</script>

<style>
</style>