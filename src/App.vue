<template>
  <div id="app">
    <todo-list>
      <div slot="title">
        <h1>Title</h1>
      </div>
      <p>I am the text from parent Component.</p>
    </todo-list>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodoList from './components/TodoList.vue'


export default {
  name: 'app',
  components: {
    HelloWorld,
    TodoList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
