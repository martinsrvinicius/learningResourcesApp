<template>
  <the-header title='RememberMe' />
  <the-resources />
</template>

<script>
import TheHeader from '@/components/layouts/TheHeader';
import TheResources from '@/components/resources/TheResources';

export default {
  components: {
    TheHeader, TheResources
  },
  name: 'App',
  }
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}

</style>