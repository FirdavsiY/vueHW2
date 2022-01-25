<template>
  <div id="app">
    <!-- v-model связывает input.value с переменной -->
    <p class="title">TODO LIST</p>

    <AddForm @ShareMyScreams="ParentFunction" />

    <main>
      <!-- Отправляем данные ребенку -->
      <TodoItem
        v-for="item of todos"
        :key="item.key"
        :block="item"
        v-on:delete_item="remove_block"
      />
    </main>
  </div>
</template>

<script>
import AddForm from "./components/AddForm.vue";
import TodoItem from "./components/TodoItem.vue";

export default {
  data() {
    return {
      todos: [
        {
          id: Math.random(),
          time: "18:44",
          title: "Купить молоко",
          isDeleted: false,
        },
        {
          id: Math.random(),
          time: "18:44",
          title: "Купить молоко",
          isDeleted: false,
        },
      ],
    };
  },
  methods: {
    ParentFunction: function (text) {
      text.length > 0 ? this.todos.push({
        id: Math.random(),
        time: new Date().getHours() + ":" + new Date().getSeconds(),
        title: text,
        isDeleted: false,
      }) : console.log('Cant add an empty task');
       
      z;
    },
    remove_block(id) {
      this.todos = this.todos.filter((del) => del.id !== id);
    },
  },
  components: {
    AddForm,
    TodoItem,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap");
#app {
  width: 1008px;
  margin: 0 auto;
  font-family: "Roboto", sans-serif;
}
main {
  margin-top: 60px;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
.title {
  text-align: calc();
  font-style: normal;
  font-weight: bold;
  font-size: 48px;
  line-height: 59px;
  text-align: center;
  margin: 0 auto;
  color: #000000;
  margin-bottom: 22px;
}
</style>
