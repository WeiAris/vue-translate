<template>
  <div id="translateOutput">
    <h2>{{translatedText}}</h2>
  </div>
</template>

<script>
export default {
  name: 'translateOutput',
  props:[
      "translatedText"
  ]
}
</script>

<style>
#translateOutput {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
