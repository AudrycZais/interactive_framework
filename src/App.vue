<template>
  <div class="container">
    <h1>Interactive Style guide</h1>
    <div><input type="checkbox" /> Light/Dark</div>
    <texts />
    <forms />
  </div>
</template>

<script>
import Texts from "./components/Texts";
import Forms from "./components/Forms";
export default {
  data() {
    return {
      vars: null,
    };
  },
  components: {
    Texts,
    Forms,
  },
};
</script>

<style lang="scss">
@import "./scss/styles.scss";
</style>
