<template>
    <div class="card">
      <div class="card-body">
        <p class="card-title">Projects</p>
        <div class="d-flex flex-wrap align-items-baseline">
          <h2 class="mr-3">{{results.projects}}% </h2>
          <i class="mdi mdi-arrow-up mr-1 text-success"></i>
          <span>
            <p class="mb-0 text-success font-weight-medium">+{{results.growth}}%</p>
          </span>
        </div>
        <p class="mb-0 text-muted">Total users world wide</p>
      </div>
      <canvas id="projects-chart"></canvas>
    </div>
</template>

<script>
export default {
  name: "TotalProjects",
  data() {
    return {
      results: {}
    };
  },
  created() {
    fetch("https://inlupp-fa.azurewebsites.net/api/total-projects")
      .then(res => res.json())
      .then(data => {
        this.results = data;
      });
  }
};
</script>

<style>
</style>