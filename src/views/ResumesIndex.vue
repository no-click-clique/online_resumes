<template>
  <div class="resume-index">
    <h1>All Resumes</h1>
    <div v-for="student in students">
      <h2>{{ student.first_name }}</h2>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      students: [],
      message: "This is the resume index."
    };
  },
  created: function() {
    axios.get("api/students").then(response => {
      this.resumes = response.data;
    });
  },
  methods: {}
};
</script>
