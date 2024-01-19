<template id="app" v-cloak>
  <div>
    <input v-model="newTodo" placeholder="新增待辦" />
    <button @click="addTodo">Add Todo</button>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">{{ todo.text }}
        <button @click="removeTodo(index)">Remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
  import { mapState, mapActions } from 'vuex';

  export default {
    data() {
        return {
        newTodo: ''
        };
    },
    computed: {
        ...mapState(['todos']),
    },
    methods: {
        ...mapActions(['addTodo', 'removeTodo']),
    }
  };
</script>