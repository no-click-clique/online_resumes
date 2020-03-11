<template>
  <div class="students-index">
    <h1>All Students</h1>
    <div v-for="student in students">
      <h2>{{ student.first_name }} {{ student.last_name }}</h2>
      <h3><img v-bind:src="student.photo" /></h3>
      <h3>{{ student.short_bio }}</h3>
      <router-link v-bind:to="`/students/${student.id}`">More Details</router-link>
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
      this.students = response.data;
    });
  },
  methods: {}
};
</script>
