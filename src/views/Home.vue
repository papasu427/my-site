<template>
  <div>
    <div ref="test" class="fullPageScroll">
      <HelloWorld id="section1" class="section section1" :num="1" />
      <HelloWorld id="section2" class="section section2" :num="2" />
      <HelloWorld id="section3" class="section section3" :num="3" />
      <HelloWorld id="section4" class="section section4" :num="4" />
    </div>

    <nav ref="pagination" class="pagination">
      <a
        v-for="pagination of page"
        :key="pagination.id"
        @click.prevent="smoothScroll($event)"
        :href="['#section' + pagination.id]"
      ></a>
    </nav>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld
  },
  data() {
    return {
      // test: this.$refs.pagination,
      page: [
        {
          title: "HOME",
          id: 1
        },
        {
          title: "ABOUT",
          id: 2
        },
        {
          title: "WORK",
          id: 3
        },
        {
          title: "CONTACT",
          id: 4
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

        if (entry.isIntersecting && entry.target.id === "section1") {
          this.observerRoot.style.backgroundColor = "#f0f4f4";
        } else if (entry.isIntersecting && entry.target.id === "section2") {
          this.observerRoot.style.backgroundColor = "#f3d9b7";
        } else if (entry.isIntersecting && entry.target.id === "section3") {
          this.observerRoot.style.backgroundColor = "#d6efdc";
        } else if (entry.isIntersecting && entry.target.id === "section4") {
          this.observerRoot.style.backgroundColor = "#f9f9d9";
        }
      });
    },
    activatePagination: function(element) {
      const newActiveIndex = document.querySelector(
        "a[href='#" + element.id + "']"
      );
      newActiveIndex.classList.add("active");
    },
    deactivatePagination: function(element) {
      const newActiveIndex = document.querySelector(
        "a[href='#" + element.id + "']"
      );
      newActiveIndex.classList.remove("active");
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
