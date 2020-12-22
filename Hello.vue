<template>
  <div>
    <p>姓名：{{ name }}</p>
    <span>年龄：{{ age }}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "xiaoxu",
      age: 25,
    };
  },
};
</script>

<style scoped></style>
