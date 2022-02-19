<template>
  <div>
    <ul>
      <li v-for="todoItem in todoItems" v-bind:key="todoItem" class="shadow">
        {{ todoItem }}
        <button class="removeBtn" v-on:click="removeToDo">remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data: function () {
    return {
      todoItems: []
    }
  },
  methods: {
    removeToDo: function () {

    },
  },
  created: function () {
    if(localStorage.length > 0){
      for (let i = 0 ; i < localStorage.length ; i++) {
        this.todoItems.push(localStorage.key(i));
      }
    }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding-left: 0;
  margin-top: 0;
  text-align: left;
}
li {
  display: flex;
  min-height: 50px;
  height: 50px;
  line-height: 50px;
  margin: 0.5rem 0;
  padding: 0 0.9rem;
  background: white;
  border-radius: 5px;
}
removeBtn {
  margin-top: auto;
  color: red;
}
</style>