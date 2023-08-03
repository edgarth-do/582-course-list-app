<template>
  <div class="card">
    <h2>Course name:</h2>
    <div>Credits:</div>
    <div>Id:</div>
    <div>Teacher:</div>
    <div>Location:</div>
    <div>Description:</div>

    <!-- <p v-if="(count = 0)">summit</p>
      <p v-else-if="count > 1 && count < 20">Allowed</p>
      <p v-else>Full</p> -->

    <button @click="innerAdd">Add</button>
    <button @click="outerAdd">Add to parent</button>
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
