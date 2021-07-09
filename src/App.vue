<template>
  <div id="app">
    <picture>
      <source media="(min-width:650px)" srcset="https://w7.pngwing.com/pngs/312/1018/png-transparent-orange-blue-and-black-logo-logo-circle-technology-circle-blue-text-information-technology.png">
      <source media="(min-width:465px)" srcset="https://w7.pngwing.com/pngs/184/1023/png-transparent-logo-nelumbo-nucifera-lotus-miscellaneous-purple-text.png">
      <img class="logo" src="https://fb.ru/misc/i/gallery/88575/2586156.jpg" alt="Logo" style="width:7%; display: block; margin: auto">
    </picture>
    <h1 class="ui dividing centered header">Vetrov Alexandr</h1>
    <div style="display: flex; width: 100%; justify-content: center; align-items: center; padding: 1.1em; ">
      <label for="switch">Сменить тему </label>
      <input type="checkbox" name="switch" id="switch" style="width: 1.1em; height: 1.1em;">
    </div>
    <div class='ui three column centered grid'>
      <div class='column'>
        <todo-list v-bind:todos="todos"></todo-list>
        <create-todo v-on:create-todo="createTodo"></create-todo>
      </div>
    </div>
    <div style="width: 600px; max-width: 100%; margin: auto; text-align: center; font-size: 1.2em; padding: 50px">Александр Ветров 191-362 <br> 9 июля 2021</div>
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
