<template>
  <div>

  </div>
</template>

<script>

</script>

<style>

</style>



<template>
 
  <div id="app"> 
    <img alt="Vue logo" src="https://cdn-icons-png.flaticon.com/512/6056/6056529.png" width="100">
    <h1>
      to do list
    </h1>
    <hr>
    <Todo_List 
    v-bind:todos="todos" 
    />
  </div>

</template>

<script>
import Todo_List from '@/components/Todo_List';
export default {
  name: 'App',
  data () {
    return {
      todos: [
        {id: 1, title: 'Купить молоко', complited: false},
        {id: 2, title: 'Купить масло', complited: false},
        {id: 3, title: 'Купить хлеб', complited: true},
        {id: 4, title: 'Купить колбасу', complited: false},
      ]

    }
  },
  components: {
    Todo_List
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>


