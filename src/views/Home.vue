<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <br />
    <h2>Here you can view Actualize Students and their resumes.</h2>
  </div>
</template>

<style>
h1 {
  color: #0099cc;
  text-align: center;
  border: 3px brown;
  overflow: auto;
  background-color: #e6a756;
}
h2 {
  color: #0099cc;
  text-align: center;
  border: 3px brown;
  overflow: auto;
  background-color: #e6a756;
}
</style>

<script>
export default {
  data: function() {
    return {
      message: "Welcome The Online Resume App!"
    };
  },
  created: function() {},
  methods: {}
};
</script>
