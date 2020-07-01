<template>
  <div>
    <div class="fullPageScroll">
      <HelloWorld id="section1" class="section" :num="1" />
      <About id="section2" class="section" :num="2" />
      <Work id="section3" class="section" :num="3" />
      <HelloWorld id="section4" class="section" :num="4" />
    </div>

    <div class="update-text">Update : 2020.05.20</div>

    <nav ref="pagination" class="pagination">
      <ul>
        <li v-for="pagination of page" :key="pagination.id">
          <a
            @click.prevent="smoothScroll($event)"
            :href="['#section' + pagination.id]"
            >{{ pagination.iconText }}</a
          >
          <p class="pagination-sub-text-size">{{ pagination.title }}</p>
          <div
            v-if="pagination.id !== page.length"
            class="pagination-line"
          ></div>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import About from "@/components/About.vue";
import Work from "@/components/Work.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
    About,
    Work
  },
  data() {
    return {
      page: [
        {
          id: 1,
          title: "HOME",
          iconText: "H"
        },
        {
          id: 2,
          title: "ABOUT",
          iconText: "A"
        },
        {
          id: 3,
          title: "WORK",
          iconText: "W"
        },
        {
          id: 4,
          title: "CONTACT",
          iconText: "C"
        }
      ]
    };
  },
  methods: {
    smoothScroll: function(event) {
      const targetId = event.target.hash;
      const target = document.querySelector(targetId);
      target.scrollIntoView({ behavior: "smooth" });
    },
    onIntersect: function(target, options = {}) {
      const observer = new IntersectionObserver(this.doWhenIntersect, options);
      // 監視したい要素をobserveする。
      observer.observe(target);
    },
    doWhenIntersect: function(entries) {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          this.activatePagination(entry.target);
        }
        if (!entry.isIntersecting) {
          this.deactivatePagination(entry.target);
        }
      });
    },
    activatePagination: function(element) {
      const newActiveIndex = document.querySelector(
        "a[href='#" + element.id + "']"
      );
      if (element.id === "section1") {
        this.observerRoot.style.backgroundColor = "#f0f4f4";
        newActiveIndex.classList.add("active1");
      } else if (element.id === "section2") {
        this.observerRoot.style.backgroundColor = "#ffdcff";
        newActiveIndex.classList.add("active2");
      } else if (element.id === "section3") {
        this.observerRoot.style.backgroundColor = "#d6efdc";
        newActiveIndex.classList.add("active3");
      } else if (element.id === "section4") {
        newActiveIndex.classList.add("active4");
        this.observerRoot.style.backgroundColor = "#f9f9d9";
      }
    },
    deactivatePagination: function(element) {
      const newActiveIndex = document.querySelector(
        "a[href='#" + element.id + "']"
      );
      if (element.id === "section1") {
        newActiveIndex.classList.remove("active1");
      } else if (element.id === "section2") {
        newActiveIndex.classList.remove("active2");
      } else if (element.id === "section3") {
        newActiveIndex.classList.remove("active3");
      } else if (element.id === "section4") {
        newActiveIndex.classList.remove("active4");
      }
    }
  },
  mounted() {
    const sections = document.querySelectorAll(".section");
    const observerRoot = document.querySelector(".fullPageScroll");
    this.observerRoot = observerRoot;
    const options = {
      root: observerRoot,
      rootMargin: "-50% 0px",
      threshold: 0
    };
    sections.forEach(target => this.onIntersect(target, options));
  }
};
</script>
<style scoped>
.section {
  width: 100%;
  height: 100vh;
  padding: 0 10%;
  scroll-snap-align: start;
}

.update-text {
  position: fixed;
  top: 1vh;
  right: 32px;
  font-size: 1vmax;
}

.fullPageScroll {
  width: 100%;
  height: 100vh;
  scroll-snap-type: y mandatory;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
  transition: 1s ease-in-out;
  background: linear-gradient(
    to right,
    rgba(76, 122, 192, 0) 0% 50%,
    rgb(255, 255, 255) 50% 100%
  );
}

.pagination {
  position: fixed;
  top: 50%;
  right: 32px;
  transform: translateY(-50%);
}

.pagination a {
  display: block;
  width: 2vmax;
  height: 2vmax;
  border-radius: 50%;
  background-color: #f0f4f4;
  transition: background-color 0.2s linear;
  transition: border-color 0.2s linear;
  border: solid 0.5vw #eeeeee;
  -webkit-box-sizing: content-box;
  -moz-box-sizing: content-box;
  box-sizing: content-box;
  text-decoration: none;
  text-decoration-color: black;
  font-size: 1.2vw;
  color: rgb(24, 24, 24);
  font-weight: 300;
  line-height: 2vw;
  margin: 0 auto;
}

.pagination a.active1 {
  border-color: #7399f9;
  background-color: #f0f4f4;
}

.pagination a.active2 {
  border-color: #f39af3;
  background-color: #ffdcff;
}

.pagination a.active3 {
  border-color: #b8edc5;
  background-color: #d6efdc;
}

.pagination a.active4 {
  border-color: #f0e463;
  background-color: #f9f9d9;
}

.pagination-sub-text-size {
  font-size: 1vw;
  font-weight: 500;
  margin-top: 4px;
}

.pagination-line {
  margin: 1vmin auto;
  width: 1px;
  height: 15px;
  background-color: black;
}
</style>
