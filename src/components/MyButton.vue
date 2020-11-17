<template>
  <a class="btn-flat-border" @click="onClick">
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: "my-button",

  methods: {
    onClick() {
      this.$emit("click");
    }
  }
};
</script>

<style scoped>
.btn-flat-border {
  display: inline-block;
  padding: 0.4em 3em;
  text-decoration: none;
  color: #424242;
  border: solid 1px #424242;
  transition: 0.4s;
  font-size: 0.8em;
}

.btn-flat-border:hover {
  background: #424242;
  color: white;
}
</style>
