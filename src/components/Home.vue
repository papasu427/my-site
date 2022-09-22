<template>
  <div class="wrapper position-re">
    <div class="scrool-box">
      <div class="scrool-arrow"></div>
      <p class="scrool-text">scrool</p>
    </div>

    <section class="wrapper-left">
      <div class="top-title">
        <div class="top-name">DAIKI TSUJIMOTO</div>
        <div class="top-subscription">
          SITE DESIGN / VIDEO EDITING / ANIMATION DESIGN / UI/UX DESIGN / CODING
          - HTML5, CSS, JavaScript
        </div>
        <myButton class="mt-5">業務・経歴一覧</myButton>
      </div>
    </section>

    <section class="wrapper-right">
      <ul class="textbox">
        <li>ウェブデザイン</li>
        <li>動画広告・編集</li>
        <li>ご依頼下さい</li>
      </ul>
    </section>
  </div>
</template>

<script>
import myButton from "@/components/MyButton.vue";
export default {
  name: "HelloWorld",
  components: {
    myButton
  },
  props: {
    msg: String,
    num: Number
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.top-subscription {
  font-size: 0.9em;
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
  left: 44%;
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
.scrool-box {
  position: absolute;
  bottom: 8vmax;
  text-align: center;
  animation: arrow-down 4s ease-in-out 0.5s infinite normal;
}
@keyframes arrow-down {
  0% {
    transform: translateY(3vmax);
    opacity: 0;
  }
  40% {
    transform: translateY(5vmax);
    opacity: 1;
  }
  100% {
    transform: translateY(5vmax);
    opacity: 0;
  }
}
.scrool-arrow {
  display: inline-block;
  width: 1.3vmax;
  height: 7vmax;
  border-bottom: 1px solid #000;
  border-left: 1px solid #000;
  transform: skewY(-45deg);
  margin-bottom: 1vmax;
  margin-left: 1vmax;
}
.scrool-text {
  font-size: 1em;
  font-weight: 200;
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

@media screen and (min-width: 〇〇px) {
  /* スタイル */
}

@media screen and (max-width: 959px) {
  .top-title {
    text-align: center;
    width: 100%;
    height: 100%;
    background: #f0f4f4;
    padding-left: 20px;
    padding-right: 20px;
    position: relative;
    top: unset;
    transform: unset;
    -webkit-transform: unset;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-flow: column;
  }
  .top-name {
    font-size: 1.5em;
    margin-bottom: 2vmin;
    font-weight: 300;
  }
  .top-subscription {
    font-size: 0.5em;
    width: 100%;
    font-weight: 300;
    line-height: 1.4;
    letter-spacing: 0.3em;
    /* text-align: center; */
    margin: 0 auto;
  }
  .textbox {
    padding: 0px;
    left: 50%;
  }
  .scrool-box {
    left: 20px;
    bottom: 5vmax;
    text-align: left;
  }
  .wrapper-left {
    height: 30vh !important;
  }

  .wrapper-right {
    height: 70vh !important;
  }
}
</style>
