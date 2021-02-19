<template>
  <div>
    Button:
    <StButton color="secondary">Dash</StButton>
    <StButton>Settings</StButton>
    Link:
    <StLink>hoveraj me burki</StLink>
  </div>
</template>

<script>
import StButton from "./components/StButton/StButton";
import StLink from "./components/StLink/StLink";
export default {
  name: "App",
  components: {
    StButton,
    StLink
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
