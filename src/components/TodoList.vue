<template>
  <div class="list">
    <todo-item
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      @todoClick="todoClick"
    ></todo-item>
  </div>
</template>

<script>
import axios from "axios";
import TodoItem from "./UI/TodoItem.vue";
export default {
  components: { TodoItem },
  data() {
    return {
      todos: [],
      limit: 4,
    };
  },
  methods: {
    async fetchPost() {
      try {
        this.isLoading = true;
        const response = await axios.get(
          "https://jsonplaceholder.typicode.com/todos",
          {
            params: {
              _limit: this.limit,
            },
          }
        );
        this.todos = response.data;
      } catch (e) {
        alert("error", e);
      } finally {
        this.isLoading = false;
      }
    },
    todoClick(item) {
      this.todos.map((todo) => {
        if (todo.id === item.id) {
          todo.complited = !todo.complited;
        }
      });
    },
  },
  mounted() {
    this.fetchPost();
  },
};
</script>

<style lang="scss" scoped>
.list {
  width: 100%;
  overflow: auto;
}
::-webkit-scrollbar {
  width: 0px;
  background: transparent;
}

html {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>