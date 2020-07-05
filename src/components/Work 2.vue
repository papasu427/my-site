<template>
  <div class="wrapper position-re">
    <section class="wrapper-left wrapper-left-add-class">
      <div class="top-name">
        <p class="top-name-boder">WORK</p>
      </div>
      <div class="top-subscription">これまでに携わった業務</div>
      <a href="#" class="btn-flat-border">BUTTON</a>
    </section>

    <section class="wrapper-right">
      <ul>
        <li class="test" v-for="(work, index) of workList" :key="index">
          <img :src="work.test" width="100%" />
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
import sq from "@/assets/img/squear.png";

export default {
  name: "Work",
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
  display: flex;
  flex-wrap: wrap;
  width: 60%;
  margin: 0 10% 0 28%;
}
.test {
  width: 50%;
  list-style: none;
  padding-right: 3px;
}
.btn-flat-border {
  display: inline-block;
  padding: 0.3em 1em;
  text-decoration: none;
  color: #67c5ff;
  border: solid 2px #67c5ff;
  border-radius: 3px;
  transition: 0.4s;
}

.btn-flat-border:hover {
  background: #67c5ff;
  color: white;
}
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
