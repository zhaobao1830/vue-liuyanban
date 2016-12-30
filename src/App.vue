<template>
  <navbar></navbar>
</template>

<script>
/* 根组件就像是 AngularJS 的 $rootScope，同时也负责全局布局 */
import Navbar from 'components/Navbar'
export default {
   components: { Navbar}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
