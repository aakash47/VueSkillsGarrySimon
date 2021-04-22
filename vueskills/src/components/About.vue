<template>
<div>
    <h1>hello {{their_name}} this is an about page</h1>
<h1>I am about Vue</h1>
<router-link v-bind:class="temp" to="/contact">Contact</router-link>
</div>
    
</template>
<script>
export default {
  name: 'Skills',
  data (){ 
  return {
      temp:{
          alert:true
      },
      their_name:this.$route.params.name
  }
  }
}
</script>
<style scoped>
.alert{
    font-size: 3rem;
    text-decoration: none;
    color:green;
}
</style>