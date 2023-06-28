<template>
  <div v-if="job">
    <h1>{{ job.title }}</h1>
    <!-- <p>The job id is {{ $route.params.id }}</p> -->
    <p>The job id is {{ id }}</p>
    <!-- no longer need the rest because I put it in data -->
    <p>{{ job.details }}</p>
  </div>
  <div v-else>
    <p>Loading job details...</p>
  </div>
</template>

<script>
  export default {
    props: ['id'],
    // data() {  // by turning on props, I don't need to do this anymore.  vid # 8, dynamic links
    //   return {
    //     id: this.$route.params.id
    //   }
    // }
    data() {
      return {
        job: null
      }
    },
    mounted() {
      fetch('http://localhost:3000/jobs/' + this.id)
      .then(res => res.json())
      .then(data => this.job = data)
      .catch(err => console.log(err.message))
    }
  }
</script>

<style scoped>

</style>