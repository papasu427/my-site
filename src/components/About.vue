<template>
  <div class="wrapper position-re">
    <section class="wrapper-left">
      <div class="top-title">
        <div class="top-name">ABOUT</div>
        <div class="top-subscription">コンセプト・受注業務について</div>
      </div>
    </section>

    <section class="wrapper-right">
      <p class="text-box">
        ウェブに特化したフリーランスウェブデザイナーです。
        <br />ユーザーファーストを軸にサイト設計からコーディングまで対応しています。
        <br />お客様がお持ちの大切な価値を利用者にわかりやすく伝えることを第一とし、
        <br />モバイル・スマートフォンに対応するためレスポンシブWebデザインにて設計します。
        <br />デザインはHTMLとCSSにて忠実に再現し、またSEOを踏まえた正しい文法でコーディングします。
        <br />SNSとの連携やサイトのメンテナンス性、運用のしやすさも重視します。
        <br />過去のクリエイティブ・制作物は可愛らしいものからシャープなものまで様々な方向性に対応していますが、
        <br />デザインの引き出しが多いというより、いずれもお客様の意図を理解しようと努力し、
        <br />閲覧者に納得していただけるものを目指した結果です。
        <br />これまでご依頼いただいていますお客様にはショップオーナー様、
        <br />企業のホームページ担当者様、また制作会社様など様々ですが、
        <br />いずれも真摯にかつ柔軟に対応しています。
        <br />ウェブサイトに関することはお気軽にご相談ください。
        <br />
      </p>
    </section>
  </div>
</template>

<script>
export default {
  name: "About",
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
.text-box {
  line-height: 2em;
  font-size: 0.7em;
  font-weight: 600;
  text-align: left;
  position: absolute;
  top: 50%;
  left: 44%;
  transform: translateY(-50%) translateX(-50%);
  -webkit-transform: translateY(-50%) translateX(-50%);
}

@media (max-height: 560px) {
  .top-name {
    font-size: 5vh;
  }
  .top-subscription {
    font-size: 3vh;
  }
  .text-box {
    font-size: 2vh;
    line-height: 4vh;
  }
}
@media (max-height: 330px) {
  .top-name {
    font-size: 7vh;
  }
  .top-subscription {
    font-size: 4vh;
  }
  .text-box {
    line-height: 5vh;
  }
}
@media screen and (max-width: 959px) {
  .top-title {
    text-align: center;
    width: 100%;
    height: 100%;
    background: #ffdcff;
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
  .top-subscription[data-v-8dc7cce2] {
    font-size: 0.5em;
    width: 100%;
    font-weight: 300;
    line-height: 1.4;
    letter-spacing: 0.3em;
    /* text-align: center; */
    margin: 0 auto;
  }
  .text-box {
    position: relative;
    left: 50%;
    padding: 20px;
  }
}
</style>
