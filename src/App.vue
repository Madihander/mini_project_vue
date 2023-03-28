<template>
  <SignUpForm/>
</template>

<script>
import SignUpForm from '@/components/SignUpForm.vue';

export default {
  components:{SignUpForm},
  data() {
    return {
    }
  },
  methods:{
  }
}


</script>

<style>
body{
  margin:0;
  background-color: #eee;
}
#app {
  font-family: Avenir,Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
