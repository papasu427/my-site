<template>
  <div class="wrapper position-re">
    <section class="wrapper-left">
      <div class="top-title">
        <div class="top-name">WORK</div>
        <div class="top-subscription">これまでに携わった業務</div>
        <!-- <a href="#" class="btn-flat-border">BUTTON</a> -->
        <myButton class="mt-5">業務・経歴一覧</myButton>
      </div>
    </section>

    <section class="wrapper-right">
      <ul class="text-box">
        <li class="test" v-for="(work, index) of workList" :key="index">
          <span>
            <img :src="work.test" />
          </span>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
import sq from "@/assets/img/squear.png";
import myButton from "@/components/MyButton.vue";

export default {
  name: "Work",
  components: {
    myButton
  },
  props: {
    msg: String,
    num: Number
  },
  data() {
    return {
      workList: [
        { test: sq },
        { test: sq },
        { test: sq },
        { test: sq },
        { test: sq },
        { test: sq },
        { test: sq },
        { test: sq }
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  display: -webkit-flex;
  display: flex;
  -webkit-justify-content: space-between;
  justify-content: space-between;
  -webkit-flex-wrap: wrap;
  flex-wrap: wrap;
  width: 40vmin;
}
.test {
  width: 49.5%;
  list-style: none;
  border: solid 1px #cfcfcf;
  margin-bottom: 2px;
  /* 正方形にするのに必要な部分 */
  height: auto;
  position: relative;
}
.test:before {
  content: "";
  display: block;
  padding-top: 100%; /* ここを100％にすることで正方形になる */
}
.test span {
  /* 正方形にするのに必要な部分 */
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  /* 中央寄せ */
  text-align: center;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  -o-box-sizing: border-box;
  -ms-box-sizing: border-box;
}
.test span:before {
  content: "";
  height: 100%;
  vertical-align: middle;
  width: 0px;
  display: inline-block;
}
.test span > * {
  vertical-align: middle;
  display: inline-block;
}

.test span img {
  max-width: 100%;
  height: auto;
  max-height: 100%;
}
.top-name-boder {
  padding-bottom: 3vmin;
  margin-bottom: 3vmin;
  border-bottom: solid 1px black;
  display: inline-block;
}
.top-subscription {
  font-size: 0.9em;
  width: 90%;
  font-weight: 300;
  line-height: 1.4;
  letter-spacing: 0.3em;
}
.text-box {
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
  .wrapper-left {
    height: 30vh !important;
  }

  .wrapper-right {
    height: 70vh !important;
  }
}
</style>
