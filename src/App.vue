<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <h1>Course List App</h1>
  <p>{{ count }}</p>
  <CourseItem @count-to-parent="addOne" />
  <courses
    :id="id"
    :course="course"
    :credits="credits"
    :location="location"
    :availability="availability"
  ></courses>
</template>

<script>
import CourseItem from "./components/CourseItem.vue";

export default {
  name: "App",
  data() {
    return {
      count: 0,
      id: "id",
      course: "course",
      credits: "credits",
      location: "location",
      availability: "availability",
      // courses: { id: 1, course: "VUE", credits: 20, location: "south" },
      // courses: [
      //   { id: 1, course: "VUE", credits: 20, location: "south" },
      //   { id: 2, course: "Powershell", credits: 35, location: "west" },
      //   { id: 3, course: "Sourcetree", credits: 18, location: "west" },
      // ],
    };
  },
  components: {
    CourseItem,
  },
  methods: {
    addOne() {
      this.count++;
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.card {
  display: inline-block;
  width: 200px;
  border: 1px solid #2c3e50;
  border-radius: 9px;
}
</style>
