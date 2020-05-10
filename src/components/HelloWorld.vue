<template>
  <div class="container">
    <section class="container-left container-left-add-class">
      <!-- 左カラム -->
      <div class="top-name">DAIKI TSUJIMOTO</div>
      <div class="top-subscription">
        SITE DESIGN / VIDEO EDITING / ANIMATION DESIGN / UI/UX DESIGN / CODING -
        HTML5, CSS, JavaScript
      </div>
    </section>
    <section class="container-right height100">
      <ul class="textbox">
        <li>ウェブデザイン</li>
        <li>動画広告・編集</li>
        <li>ご依頼下さい</li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    num: Number
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container-left-add-class {
  left: -4vw;
}
.top-name {
  font-size: 2em;
  margin-bottom: 2vmin;
  font-weight: 300;
}
.top-subscription {
  font-size: 1em;
  width: 90%;
  font-weight: 300;
  line-height: 1.4;
  letter-spacing: 0.3em;
}
.textbox {
  position: absolute;
  writing-mode: vertical-rl;
  text-orientation: upright;
  top: 50%;
  left: 56%;
  transform: translateY(-50%) translateX(-50%);
  -webkit-transform: translateY(-50%) translateX(-50%);
  text-align: left;
  font-size: 2em;
  font-weight: bold;
}

.textbox li {
  margin-left: 4vmin;
  background-color: yellow;
}

.textbox li:last-child {
  margin-left: 0;
  background-color: #fff;
}

@media (max-height: 560px) {
  .top-name {
    font-size: 5vh;
  }
  .top-subscription {
    font-size: 3vh;
  }
  .textbox {
    font-size: 5vh;
  }
}
@media (max-height: 330px) {
  .top-name {
    font-size: 7vh;
  }
  .top-subscription {
    font-size: 4vh;
  }
}
</style>
