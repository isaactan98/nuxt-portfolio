<template>
  <div class="center vh-95">
    <div class="details">
      <div class="center"><h1>My Recent Work</h1></div>
      <div class="example">
        <div class="">
          <div style="" class="center">
            <vs-card-group>
              <vs-card :key="card" v-for="card in 8" @click="handleClick">
                <template #title>
                  <h3>Pot with a plant {{ card }}</h3>
                </template>
                <template #img>
                  <img src="../components/me.jpg" alt="" />
                </template>
                <template #text>
                  <p>
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                  </p>
                </template>
                <template #interactions>
                  <vs-button danger icon>
                    <i class="bx bx-heart"></i>
                  </vs-button>
                  <vs-button class="btn-chat" shadow primary>
                    <i class="bx bx-chat"></i>
                    <span class="span"> 54 </span>
                  </vs-button>
                </template>
              </vs-card>
            </vs-card-group>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handleClick() {},
  },
};
</script>

<style>
.details {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem 2.5rem;
}
.example {
  padding: 10px;
  border-radius: 5px 20px 0 0;
  border-bottom: 0 solid rgba(0, 0, 0, 0.03);
  position: relative;
  overflow: hidden;
  transition: all 0.25s ease;
  height: auto;
}
.example::before {
  width: 60px;
  height: 25px;
  left: 50%;
  transform: translate(-50%);
  border-radius: 0 0 8px 8px;
  transition: all 0.25s ease;
  content: "";
  position: absolute;
  box-sizing: border-box;
  top: 0;
  pointer-events: none;
  opacity: 0;
  visibility: hidden;
}
.example::after {
  width: 100%;
  height: 100%;
  left: 0;
  border-radius: 25px;
  transition: all 0.25s ease;
  content: "";
  position: absolute;
  box-sizing: border-box;
  top: 0;
  pointer-events: none;
  opacity: 0;
  visibility: hidden;
}

.vs-card__group-cards > .vs-card-content > .vs-card > .vs-card__img {
  max-height: 250px !important;
}

@media screen and (max-width: 414px) {
  .details {
    max-width: 350px;
    padding: 10px;
  }
}
</style>