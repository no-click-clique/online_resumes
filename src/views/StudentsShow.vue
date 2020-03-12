<template>
  <div class="home">
    <div class="container">
      <img v-bind:src="student.photo" alt="" />
      <!-- <img v-bind:src="student.photo" alt="">
      <h1>{{ student.first_name }} {{ student.last_name }}</h1>
      <span>
        Email: {{ student.email }}, Phone: {{ student.phone_number }}, LinkedIn: {{ student.linkedin_url }}, Twitter:
        {{ student.twitter_handle }}
      </span>
      <h3>{{ student.short_bio }}</h3>
      Skills:
      <span v-for="skill in student.skills">{{ skill.name }},</span>
      <div v-for="experience in student.experiences">
        <h3>Experiences:</h3>
        Company:
        <span>{{ experience.company_name }}</span>
        <br />
        Job Title:
        <span>{{ experience.job_title }}</span>
        <br />
        Job Description:
        <span>{{ experience.details }}</span>
        <br />
        Start Date:
        <span>{{ experience.start_date }}</span>
        <br />
        End Date:
        <span>{{ experience.end_date }}</span>
        <br />
      </div>
      <div v-for="education in student.educations">
        <h3>Education:</h3>
        School:
        <span>{{ education.university_name }}</span>
        <br />
        Degree:
        <span>{{ education.degree }}</span>
        <br />
        Program:
        <span>{{ education.details }}</span>
        <br />
        Start Date:
        <span>{{ education.start_date }}</span>
        <br />
        End Date:
        <span>{{ education.end_date }}</span>
        <br />
      </div>
      <div v-for="capstone in student.capstones">
        <h3>Capstone:</h3>
        Name:
        <span>{{ capstone.name }}</span>
        <br />
        Description:
        <span>{{ capstone.description }}</span>
        <br />
        Website:
        <span>{{ capstone.url }}</span>
        <br />
        Screenshot:
        <span>{{ capstone.screenshot }}</span>
        <br />
      </div>

 -->
      <section class="page-section clearfix">
        <div class="container">
          <div class="intro">
            <img class="intro-img img-fluid mb-3 mb-lg-0 rounded" v-bind:src="student.photo" alt="" />
            <div class="intro-text left-0 text-center bg-faded p-5 rounded">
              <h2 class="section-heading mb-4">
                <span class="section-heading-lower">{{ student.first_name }} {{ student.last_name }}</span>
                <span class="section-heading-upper">{{ student.email }}</span>
                <span class="section-heading-upper">Ph: {{ student.phone_number }}</span>
                <span class="section-heading-upper">{{ student.linkedin_url }}</span>
                <span class="section-heading-upper">{{ student.twitter_handle }}</span>
              </h2>
              Skills:
              <span v-for="skill in student.skills">{{ skill.name }},</span>
              <br />
              <br />

              <div v-for="experience in student.experiences">
                <h3>Experiences</h3>
                Company:
                <span>{{ experience.company_name }}</span>
                <br />
                Job Title:
                <span>{{ experience.job_title }}</span>
                <br />
                Job Description:
                <span>{{ experience.details }}</span>
                <br />
                Start Date:
                <span>{{ experience.start_date }}</span>
                <br />
                End Date:
                <span>{{ experience.end_date }}</span>
                <br />
              </div>
              <br />
              <br />
              <div v-for="education in student.educations">
                <h3>Education</h3>
                School:
                <span>{{ education.university_name }}</span>
                <br />
                Degree:
                <span>{{ education.degree }}</span>
                <br />
                Program:
                <span>{{ education.details }}</span>
                <br />
                Start Date:
                <span>{{ education.start_date }}</span>
                <br />
                End Date:
                <span>{{ education.end_date }}</span>
                <br />
              </div>
              <br />
              <br />
              <div v-for="capstone in student.capstones">
                <h3>Capstone</h3>
                Name:
                <span>{{ capstone.name }}</span>
                <br />
                Description:
                <span>{{ capstone.description }}</span>
                <br />
                Website:
                <span>{{ capstone.url }}</span>
                <br />
                Screenshot:
                <span>{{ capstone.screenshot }}</span>
                <br />
              </div>
              <!--  <p class="mb-3">Every cup of our quality artisan coffee starts with locally sourced, hand picked ingredients. Once you try it, our coffee will be a blissful addition to your everyday morning routine - we guarantee it!
              </p> -->
              <!--  <div class="intro-button mx-auto">
                <a class="btn btn-primary btn-xl" href="#">Visit Us Today!</a>
              </div> -->
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      student: {},
      educations: [],
      experiences: [],
      capstones: [],
      skills: []
    };
  },

  created: function() {
    axios.get(`/api/students/${this.$route.params.id}`).then(response => {
      this.student = response.data;
    });
  },

  methods: {}
};
</script>
