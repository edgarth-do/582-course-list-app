<template>
  <div class="card">
    <h2>{{ course.name }}</h2>
    <p>{{ course.description }}</p>
    <ul>
      <li>{{ course.credits }}</li>
      <li>{{ course.id }}</li>
      <li>{{ course.teacher }}</li>
      <li>{{ course.location }}</li>
    </ul>

    <button @click="sendAdd">Add Course</button>
    <button @lick="sendRemove">Remove Course</button>
  </div>
</template>

<script>
export default {
  name: "CourseItem",
  props: {
    id: {
      type: Number,
      required: true,
    },
    course: {
      type: String,
      required: true,
    },
    credits: {
      type: Number,
      required: true,
    },
    location: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      count: 0,
      id: "id",
      course: "course",
      credits: "credits",
      location: "location",
      availability: "availability",
    };
  },
  methods: {
    innerAdd() {
      this.count++;
    },
    outerAdd() {
      this.$emit("count-to-parent");
    },
  },
};
</script>
