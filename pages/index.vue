
<template>
  <div class="vh-95 center">
    <div class="center grid al-c vh-95">
      <vs-row>
        <vs-col vs-type="flex" vs-justify="center" vs-align="center" lg="6" sm="12" xs="12">
          <div class="center">
            <div class="">
              <h1 class="hero-title">Hi, I'm Isaac Tan.</h1>
              <p class="hero-text">
                I'm a Web Developer, Photographer and a Student. I also like to
                try different things in life.
              </p>
            </div>
          </div>
        </vs-col>
        <vs-col vs-type="flex" vs-justify="center" vs-align="center" lg="6" sm="12" xs="12">
          <div class="center">
            <vs-card type="2">
              <template #title>
                <h3>You're in the GAME now</h3>
              </template>
              <template #img>
                <img src="../components/me.jpg" alt="" />
              </template>
              <template #text>
                <p>May as well put forth on your best effort.</p>
              </template>
            </vs-card>
          </div>
        </vs-col>
      </vs-row>
    </div>
    <HomeDetails />
    <Footers/>
  </div>
</template>
<script>
import Footers from '~/components/Footer.vue';
import HomeDetails from "~/components/HomeDetails.vue";
export default {
  head: {
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "This is a portfolio for Isaac Tan, including Recent Work, About, and Contact Page.",
      },
      {
        hid: "keywords",
        name: "keywords",
        content:
          "portfolio, Isaac Tan, Isaac Tan Yu Hao, isaactan.website, Isaac Tan Portfolio, ",
      },
      {
        hid: "robots",
        name: "robots",
        content: "index, follow",
      },
    ],
  },
  components: { HomeDetails, Footers },
  data() {
    return {
      active: "home",
    };
  },
};
</script>

<style>
.al-c {
  align-items: center !important;
}
.vs-row {
  align-items: center !important;
}
.hero-title {
  font-size: 4.2em;
  letter-spacing: -1.5px;
  line-height: 110%;
  margin: 0;
}
.hero-text {
  font-size: 1.1em;
  line-height: 1.7;
  padding-right: 2em;
  font-family: Biotif-Regular, Helvetica Neue, Helvetica, Arial, sans-serif;
}
.vs-card__img {
  max-height: 750px !important;
}

@media screen and (max-width: 414px) {
  .center {
    padding: 10px !important;
  }
  .hero-title {
    font-size: 3em;
  }
}
</style>

        