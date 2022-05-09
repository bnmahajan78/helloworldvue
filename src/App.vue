<template>
    <img alt="Vue logo" src="./assets/logo.png">

    <HelloWorld msg="Place holder for component 1" />

    <ImagePic msg="Place holder for component 2" />

</template>

<script>
    import HelloWorld from './components/HelloWorld.vue'
    import ImagePic from './components/ImagePic.vue'


export default {
  name: 'App',
  components: {
      HelloWorld,
      ImagePic
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
