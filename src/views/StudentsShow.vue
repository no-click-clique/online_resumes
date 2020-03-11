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

      <section class="page-section cta">
        <div class="container">
          <div class="row">
            <div class="col-xl-9 mx-auto">
              <div class="cta-inner text-center rounded">
                <h2 class="section-heading mb-4">
                  <!-- <span class="section-heading-upper">{{ student.email }}</span> -->
                  <span class="section-heading-lower">{{ student.first_name }} {{ student.last_name }}</span>
                  <span class="section-heading-upper">Email: {{ student.email }}</span>
                  <span class="section-heading-upper">Phone: {{ student.phone_number }}</span>
                  <span class="section-heading-upper">Linkedin: {{ student.linkedin_url }}</span>
                  <span class="section-heading-upper">Twitter: {{ student.twitter_handle }}</span>

                </h2>
                <p class="mb-0">When you walk into our shop to start your day, we are dedicated to providing you with friendly service, a welcoming atmosphere, and above all else, excellent products made with the highest quality ingredients. If you are not satisfied, please let us know and we will do whatever we can to make things right!</p>
              </div>
            </div>
          </div>
        </div>
      </section>
      
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