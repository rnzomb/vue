<template>
    <div>
      <NameForm initial-name ="asdf" initial-surname="ghjy" />
      <hr>
      <HumanStats  />
  </div>
</template>

<script>

import NameForm from '@/components/NameForm'
import HumanStats from '@/components/HumanStats'
export default {
  name: 'app',
  components: {
    NameForm,
    HumanStats
    
  }
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
