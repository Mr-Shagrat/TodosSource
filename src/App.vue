<template>
  <div class="wrapper">
    <div class="rectangle-1"></div>
    <div class="rectangle-2"></div>
    <todos-form></todos-form>
  </div>
</template>

<script>
import TodosForm from "./components/TodosForm.vue";
export default {
  components: { TodosForm },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: #ffffff;
  font-family: "Montserrat", sans-serif;
  font-style: normal;
  font-weight: normal;
}

.wrapper {
  position: relative;
  max-width: 420px;
  height: 540px;
}
.rectangle-1,
.rectangle-2 {
  position: absolute;
  border-radius: 20px;
}
.rectangle-1 {
  width: 81.4%;
  height: 85.23px;
  left: 2px;
  top: -14.32px;
  background: #4f5565;
  transform: rotate(-4.48deg);
}
.rectangle-2 {
  width: 94.07%;
  height: 67.97px;
  left: 0;
  top: -9.32px;
  background: #31394d;
  transform: rotate(-2.32deg);
  z-index: 1;
}

#app {
  padding: 0 15px;
  min-height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #010920;
}
</style>