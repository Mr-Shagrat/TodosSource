<template>
  <div class="todo">
    <div class="checkbox">
      <input
        class="custom-checkbox"
        type="checkbox"
        :id="todo.id"
        :name="todo.id"
      />
      <label :for="todo.id" @click="todoClick">
        <div class="todo__description">
          <div class="todo__title">{{ todo.title }}</div>
          <div class="todo__label" v-if="randomDescription">
            {{ todo.title }}
          </div>
        </div>
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: "MyItem",
  props: {
    todo: {
      required: true,
      type: Object,
    },
  },
  methods: {
    todoClick(event) {
      this.$emit("todoClick", this.todo);
    },
  },
  computed: {
    randomDescription() {
      return Math.floor(Math.random() * (4 - 1 + 1)) + 1 === 1;
    },
  },
};
</script>

<style lang="scss">
.todo {
  padding: 9px 0;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  &__checkbox {
    margin-right: 15px;
  }
  &__decription {
    display: flex;
    flex-direction: column;
  }
  &__title {
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: #ffffff;
  }
  &__label {
    font-size: 12px;
    line-height: 15px;
    color: #4f5565;
    margin-top: 3px;
  }
}

/* для элемента input c type="checkbox" */
.custom-checkbox {
  position: absolute;
  z-index: -1;
  opacity: 0;
}

/* для элемента label, связанного с .custom-checkbox */
.custom-checkbox + label {
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  user-select: none;
}
.custom-checkbox:not(:checked) + label {
  &:hover {
    .todo__title,
    .todo__label {
      color: #ff8469;
    }
    &::before {
      background-color: rgba(255, 132, 105, 0.2);
    }
  }
}
.custom-checkbox:checked + label {
  .todo__title,
  .todo__label {
    color: #4f5565;
    text-decoration: line-through;
  }
  &:hover {
    .todo__title,
    .todo__label {
      color: #fff;
      text-decoration: line-through;
    }
    &::before {
      background-color: #ff8469;
    }
  }
}
/* создание в label псевдоэлемента before со следующими стилями */
.custom-checkbox + label::before {
  cursor: pointer;
  content: "";
  display: block;
  width: 20px;
  height: 20px;
  flex-shrink: 0;
  flex-grow: 0;
  margin-right: 15px;
  background: #4f5565;
  border-radius: 6px;
}

/* стили для чекбокса, находящегося в состоянии checked */
.custom-checkbox:checked + label::before {
  background-color: #ff8469;
  background-image: url("../../assets/check.svg");
  background-repeat: no-repeat;
  background-position: center;
  background-size: 12px;
}
</style>