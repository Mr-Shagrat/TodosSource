<template>
  <div class="form">
    <div class="form__header">
      <h3 class="form__title">Todo list</h3>
      <my-button>add</my-button>
    </div>
    <todo-list></todo-list>
  </div>
</template>

<script>
import MyButton from "./UI/MyButton.vue";
import TodoList from "./TodoList.vue";
export default {
  components: { MyButton, TodoList },
};
</script>

<style lang="scss" scoped>
.form {
  overflow: hidden;
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 30px;
  width: 100%;
  height: 100%;
  background: #252e42;
  box-shadow: 0px 14px 34px rgba(0, 0, 0, 0.25);
  border-radius: 20px;
  &__header {
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin-bottom: 20px;
  }
  &__title {
    font-weight: bold;
    font-size: 28px;
    line-height: 34px;
  }
}
</style>