<template>
  <header>
    <h3 class="header-title">Monster Slayer</h3>
  </header>
  <FriendContact msg="Welcome to Your Vue.js App" />
</template>

<script>
import FriendContact from "./components/FriendContact.vue";

export default {
  name: "App",
  components: {
    FriendContact,
  },
};
</script>

<style lang="scss">
header {
  height: 100px;
  background-color: #123456;

  .header-title {
    color: white;
    line-height: 100px;
    font-size: 30px;
  }
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body,
* {
  margin: 0;
  padding: 0;
}
</style>
