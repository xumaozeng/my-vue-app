<template>
  <div>
    <!-- 用户输入 -->
    <p>
      <input type="text" v-model="val" @keydown.enter="addCourse" class="inp" />
      <button @click="addCourse">新增</button>
    </p>
    <!-- 条件渲染 -->
    <p v-if="courses.length === 0">没有任何课程信息</p>

    <!-- 列表渲染 -->
    <div
      v-else
      v-for="c in courses"
      :key="c.name"
      :class="{ active: selectedCourse === c }"
      @click="selectedCourse = c"
    >
      {{ c.name }} - {{ c.price | currency("￥") }}
    </div>
  </div>
</template>

<script>
import { getCourses } from "@/api/course";
export default {
  data() {
    return {
      selectedCourse: "",
      courses: [],
      val: "",
    };
  },
  filters: {
    currency(value, symbol = "￥") {
      return symbol + value;
    },
  },
  async created() {
    const result = await getCourses();
    this.courses = result;
  },
  methods: {
    onClick(c) {
      this.selectedCourse = c;
    },
    addCourse() {
      if (this.val) {
        this.courses.push({ name: this.val, price: 2300 });
        this.val = "";
      }
    },
  },
};
</script>

<style scoped>
.active {
  background-color: #ddd;
}
.red {
  color: #f00;
}
.inp {
  margin: 5px;
}
</style>