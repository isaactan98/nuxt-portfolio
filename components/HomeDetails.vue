<template>
  <div class="center grid vh-95 titles">
    <div class="vs-card title">
      <span class="category">Photography</span>
      <h2>Food Photography</h2>
      <div></div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.titles {
  position: relative;
  z-index: 1000;
  margin: 4em auto 0;
  max-width: 90%;
  display: -ms-grid;
  display: grid;
  gap: 4em;
  grid-template-columns: repeat(1, 1fr);
}
.title {
  margin: auto;
  width: 100%;
  border-radius: 20px;
  position: relative;
  display: block;
  transition: all 0.4s ease-in-out;
  padding: 3em 3em 4em;
  box-sizing: border-box;
  cursor: pointer;
  text-decoration: none;
}
.category {
  display: block;
  font-family: Biotif-Regular, Helvetica Neue, Helvetica, Arial, sans-serif;
  font-size: 14px;
  opacity: 0.6;
  text-align: left;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  font-weight: 700;
}
</style>