<template>
  <div id="app">
    <Header />
    <Container/>
  </div>
</template>

<script>


import Container from "./components/container";
import Header from "./components/header"
export default {
  name: 'App',
  components: {
    Container,
    Header
  },
  data(){
    return {

    }
  },
  methods: {

  }
}
</script>

<style>

</style>
