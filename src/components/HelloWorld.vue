<template>
  <div>{{ num }}</div>
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
<style scoped></style>
