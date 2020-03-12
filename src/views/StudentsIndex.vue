<template>
  <div class="students-index">
   <!--  <h5>All Students</h5>
    <div v-for="student in students">
      <h2>{{ student.first_name }} {{ student.last_name }}</h2>
      <h3><img v-bind:src="student.photo" /></h3>
      <h3>{{ student.short_bio }}</h3>
      <router-link v-bind:to="`/students/${student.id}`">More Details</router-link>
    </div> -->

    <section v-for="student in students" class="page-section clearfix">
      <div class="container">
        <div class="intro">
          <img class="intro-img img-fluid mb-3 mb-lg-0 rounded" v-bind:src="student.photo" alt="">
          <div class="intro-text left-0 text-center bg-faded p-5 rounded">
            <h2 class="section-heading mb-4">
              <span class="section-heading-upper">Actualize Graduate</span>
              <span class="section-heading-lower">{{ student.first_name }} {{ student.last_name }}</span>
            </h2>
            <p class="mb-3">{{ student.short_bio }}</p>
            <div class="intro-button mx-auto">
              <router-link v-bind:to="`/students/${student.id}`" class="btn btn-primary btn-xl" href="#">Resume</router-link>
            </div>
          </div>
        </div>
      </div>
    </section>


  </div>
</template>

<style></style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      students: [],
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
