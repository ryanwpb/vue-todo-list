<template>
  <div id="app">{{msg}}</div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      msg: "Hello World"
    };
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
