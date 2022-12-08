<template>
  <page-header title="Give me Advice" text='Provide a number ang det a piece of advice'></page-header>
  <PageForm />
</template>
<script>
import PageHeader from './components/PageHeader.vue';
import PageForm from './components/PageForm.vue';
import data from '../data.json';
export default {
  name: 'App',
  components: {
    PageHeader,
    PageForm,
  },
  provide(){
    return{
      newarr: this.data,
      message:'heeeelllllllloo',
    }
  },
  data(){
    return {
      data,
    }
  }
}
</script>

<style>
@import './assets/css/style.css';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
