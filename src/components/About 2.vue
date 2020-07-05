<template>
  <div class="wrapper position-re">
    <section class="wrapper-left wrapper-left-add-class">
      <div class="top-name">
        <p class="top-name-boder">ABOUT</p>
      </div>
      <div class="top-subscription">コンセプト・受注業務について</div>
    </section>

    <section class="wrapper-right">
      <p class="text-box">
        ウェブに特化したフリーランスウェブデザイナーです。
        <br />自ら行うグラフィックデザインを軸にサイト設計からコーディングまで対応しています。
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
.wrapper-left-add-class {
  left: -4vw;
}
.top-name-boder {
  padding-bottom: 3vmin;
  margin-bottom: 3vmin;
  border-bottom: solid 1px black;
  display: inline-block;
}
.top-name {
  font-size: 1.9em;
  font-weight: 300;
}
.top-subscription {
  font-size: 0.9em;
  width: 90%;
  font-weight: 300;
  line-height: 1.4;
  letter-spacing: 0.3em;
}
.text-box {
  padding: 0 2% 0 10%;
  margin: 0 auto;
  line-height: 2em;
  font-size: 0.7em;
  font-weight: 600;
  text-align: left;
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
</style>
