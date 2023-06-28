<template>
  <h1>Job Details Page</h1>
  <!-- <p>The job id is {{ $route.params.id }}</p> -->
  <p>The job id is {{ id }}</p>
  <!-- no longer need the rest because I put it in data -->
  <div>

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
  }
</script>

<style scoped>

</style>