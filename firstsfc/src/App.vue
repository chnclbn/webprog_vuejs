<template>
  <div id="app">
    <personal-profile></personal-profile>
  </div>

  <div class="food-container">
    <food-item />
    <food-item2 />
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


.food-container {
  display: flex;   
  gap: 20px;       
</style>