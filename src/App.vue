<template>
  <div id="app">
    Check Console Log in browser for OpenGraph data.....
  </div>
</template>

<script>

const ogs = require('open-graph-scraper-lite');

export default {
  name: 'app',
  mounted() {
    const options = {
      url: 'http://ogp.me/',
    };
    ogs(options)
      .then((data) => {
        const { error, result, response } = data;
        console.log('error:', error);  // This is returns true or false. True if there was a error. The error it self is inside the results object.
        console.log('result:', result); // This contains all of the Open Graph results
        console.log('response:', response); // This contains the HTML of page
      })
  }
};
</script>

<style scoped>


</style>
