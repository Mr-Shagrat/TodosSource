<template>
  <div class="wrapper">
    <div class="rectangle-1"></div>
    <div class="rectangle-2"></div>
    <todos-form class="wrapper__form"></todos-form>
    <h3 class="wrapper__footer">© 2021. Schigolev A.</h3>
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
  margin-top: 162px;
  position: relative;
  width: 420px;
  height: 540px;
  @media (max-width: 450px) {
    max-width: 420px;
    min-width: 250px;
    margin-top: 100.5px;
  }
  &__form {
    margin-bottom: 30px;
  }
  &__footer {
    cursor: default;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: #252e42;
    text-align: center;
  }
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
  top: -26px;
  background: #4f5565;
  transform: rotate(-4.48deg);
}
.rectangle-2 {
  width: 94.1%;
  height: 67.97px;
  left: 1px;
  top: -16.5px;
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
  background: #010920;
}
</style>