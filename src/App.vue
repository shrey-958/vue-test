<template>
  <div id="app">
    <Header />
    <CubeNum />
   
  </div>
</template>

<script>
import Header from './components/Header'
import CubeNum from './components/CubeNum'





export default {
  name: 'App',
  components: {
    Header,
    CubeNum
    
  }
}
  
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

</style>
