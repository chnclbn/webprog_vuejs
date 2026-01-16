<template>
  <div id="app">
    <personal-profile></personal-profile>
  </div>
</template>

<script>

import PersonalProfile from './components/PersonalProfile.vue'

export default {
  name: 'App',
  components: {
  
    PersonalProfile
  }
}
</script>

<style>

body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>