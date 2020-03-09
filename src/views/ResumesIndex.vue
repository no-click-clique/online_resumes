<template>
  <div class="resume-index">
    <h1>All Resumes</h1>
  </div>
</template>

<style></style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      resumes: []
    };
  },
  created: function() {
    axios.get("api/resumes").then(response => {
      this.resumes = response.data;
    });
  },
  methods: {}
};
</script>
