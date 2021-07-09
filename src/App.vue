<template>
  <div id="app">
    <h1 class="ui dividing centered header">Vetrov Alexandr 191-362</h1>
    <div class='ui three column centered grid'>
      <div class='column'>
        <todo-list v-bind:todos="todos"></todo-list>
        <create-todo v-on:create-todo="createTodo"></create-todo>
      </div>
    </div>
  </div>
</template>

<script>
import sweetalert from 'sweetalert';
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'app',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [{
        title: 'Task 1',
        project: 'Project A',
        done: false,
      }, {
        title: 'Task 2',
        project: 'Project B',
        done: false,
      }, {
        title: 'Task 3',
        project: 'Project C',
        done: false,
      }, {
        title: 'Task 4',
        project: 'Project D',
        done: false,
      }],
    };
  },
  methods: {
    createTodo(newTodo) {
      this.todos.push(newTodo);
      sweetalert('Success!', 'To-Do created!', 'success');
    },
  },
};
</script>
