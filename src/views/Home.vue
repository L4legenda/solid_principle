<template>
  <div>
    <Header listName="My new todo list" />
    <main>
      <todo-list>
        <todo-card v-for="todo in todos" :key="todo.id" :todo="todo" />
      </todo-list>
    </main>
  </div>
</template>

<script lang="ts" setup>

import { ITodo } from "../types";
import { reactive, onMounted } from "vue";
import Header from "@/components/Header.vue";
import TodoList from "@/components/TodoList.vue";
import TodoCard from "@/components/TodoCard.vue";
import { AxiosApi } from "@/AxiosApi";

let todos: ITodo[] = reactive([]);

async function fetchTodos(todos: ITodo[]): Promise<ITodo[]> {

  const api = new AxiosApi();
  return await api.fetch("todos");

}

onMounted(async () => {
  let data = await fetchTodos(todos);
  for (let item of data) {
    todos.push(item);
  }
});

</script>