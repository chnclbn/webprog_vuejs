<template>
  <div class ="coffee2">
    <h2>{{ name }}</h2>
    <p>{{ message }}</p>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      name: 'Iced coffee that I like:)',
      message: 'I like cold brew and caramel macchiato'
    }
  }
};
</script>
<style>
 .coffee2 {
    border: dashed black 1px;
    display: inline-block;
    margin: 10px;
    padding: 10px;
    background-color: pink;
  }
</style>