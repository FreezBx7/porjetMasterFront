<template>
  <div id="app">
    <div v-for="training in allTrainings" :key=training.id_training>
      {{training.name}}
    </div>
  </div>
</template>

<script>
import gql from 'graphql-tag';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  apollo: {
    allTrainings: gql`
      query {
      allTrainings {
        id_training
        name
      }
    }
    `
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
