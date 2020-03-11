<template>
  <div class="home">
    
    <div class="container">
      <img v-bind:src="student.photo" alt="">
      <h1>{{ student.first_name }} {{ student.last_name }}</h1>
      <span>Email: {{ student.email }}, Phone: {{ student.phone_number }}, LinkedIn: {{ student.linkedin_url }}, Twitter: {{ student.twitter_handle }} </span>
      <h3>{{ student.short_bio }}</h3>
      Skills: <span v-for="skill in student.skills">{{ skill.name }}, </span>
        <div v-for="experience in student.experiences">
          <h3>Experiences:</h3> 
          Company: <span>{{ experience.company_name }}</span><br>
          Job Title: <span>{{ experience.job_title }}</span><br>
          Job Description: <span>{{ experience.details }}</span><br>
          Start Date: <span>{{ experience.start_date }}</span><br>
          End Date: <span>{{ experience.end_date }}</span><br>
        </div>
         <div v-for="education in student.educations">
          <h3>Education:</h3> 
          School: <span>{{ education.university_name }}</span><br>
          Degree: <span>{{ education.degree }}</span><br>
          Program: <span>{{ education.details }}</span><br>
          Start Date: <span>{{ education.start_date }}</span><br>
          End Date: <span>{{ education.end_date }}</span><br>
        </div>
         <div v-for="capstone in student.capstones">
          <h3>Capstone:</h3> 
          Name: <span>{{ capstone.name }}</span><br>
          Description: <span>{{ capstone.description }}</span><br>
          Website: <span>{{ capstone.url }}</span><br>
          Screenshot: <span>{{ capstone.screenshot }}</span><br>
        </div>
      </div>
      
    </div>
   

  </div>
</template>

<style>
</style>

<script>
import axios from 'axios';

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
    axios
      .get("/api/students/1")
      .then(response => {
        this.student = response.data;
      });
  },

  methods: {}
};
</script>