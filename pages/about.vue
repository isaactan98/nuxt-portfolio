<template>
  <div class="vh-95">
    <div class="center">
      <h2>About</h2>
    </div>
    <div class="center">
      <vs-card type="5">
        <template #title>
          <h3>This is ME</h3>
        </template>
        <template #img>
          <img src="../components/me.jpg" alt="" />
        </template>
        <template #text>
          <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit.</p>
        </template>
        <template #interactions>
          <vs-button danger icon>
            <i class="bx bx-heart"></i>
          </vs-button>
        </template>
      </vs-card>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    active: "docs",
  }),
};
</script>

<style>
.vs-card__img {
  max-height: 300px;
}
</style>