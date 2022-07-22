<script lang="ts">
  import type { ITodo } from '../type'
  import Todo from './Todo.svelte'

  export let todoList: ITodo[] = []
</script>

<div class="wrapper">
  <div class="todo-list">
    <h2>Pending</h2>
    {#each todoList.filter((t) => !t.isCheck) as todo, i (todo.id)}
      <Todo bind:todo />
    {/each}
  </div>
  <div class="todo-list">
    <h2>Done</h2>
    {#each todoList.filter((t) => t.isCheck) as todo, i (todo.id)}
      <Todo bind:todo />
    {/each}
  </div>
</div>

<style>
  .todo-list {
    padding: 20px;
    margin: 0px auto;
  }

  .wrapper {
    width: 800px;
    margin: auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
</style>
