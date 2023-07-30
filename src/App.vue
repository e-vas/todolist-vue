<template>
 
  <div id="app"> 
    <img alt="Vue logo" src="https://cdn-icons-png.flaticon.com/512/6056/6056529.png" width="100">
    <h1>
      to do list
    </h1>
    <hr>
    <input 
    type="text" 
    placeholder="Add task" 
    v-model="newTask"
    />
    <button
    v-on:click="inputGetValue"
    > Add</button>
    <hr>
        <!-- <TodoList 
    v-bind:todos="todos" 
    /> -->

    <ul v-for="(item, index) in todos" :key="item.id">
      <li>
        <input type="checkbox" 
        v-on:click="checBoxTask(index)"
        v-bind:checked="item.complited"
        /> 
        <span>{{ item.title }}</span>
        <button
        v-on:click="deleteTask(index)"
        > &#x2716; </button>
      </li>
      
    </ul>
  
  </div>

</template>

<script>
//import TodoList from '@/components/TodoList';
export default {
  name: 'App',
  data () {
    return {
      todos: [
        {id: 1, title: 'Купить молоко', complited: false},
        {id: 2, title: 'Купить масло', complited: true},
        {id: 3, title: 'Купить хлеб', complited: true},
        {id: 4, title: 'Купить колбасу', complited: false},
      ],
      newTask: " ",

    }
    

  },
  methods: {
    inputGetValue () {
      let uuid = Date.now();
      this.todos.push({id: uuid, title: this.newTask, complited: false})
      this.newTask = " "
      
    },
    checBoxTask (index) {
      if (this.todos[index].complited === true) {
        this.todos[index].complited = false
      } else {
        this.todos[index].complited = true
      }
      console.log(this.todos[index].complited)

    },
    deleteTask (index) {
      this.todos.splice(index, 1)
      console.log(index)
     
    }

  },
  components: {
    //TodoList
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
