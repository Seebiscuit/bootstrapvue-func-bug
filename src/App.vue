<template>
  <div id="app">
    <div id="nav">
      <b-icon
        icon="gear-fill"
        aria-hidden="true"
      ></b-icon>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
    <b-calendar
      v-model="value"
      @context="onContext"
      locale="en-US"
    ></b-calendar>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

/* This DOES NOT Work */
export default class App extends Vue {
  public data() {
    return {
      value: "",
    };
  }
}

//* This Works:
/*
export default Vue.extend({
  data() {
    return {
      value: "",
    };
  },
});
*/
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
