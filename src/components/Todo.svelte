<script lang="ts">
  import { fade, fly } from 'svelte/transition'

  interface ITodo {
    id: number
    isCheck: boolean
    title: string
    description: string
  }

  let isExplain = false

  export let todo: ITodo
</script>

<div class="todo" in:fly={{ y: 200, duration: 2000 }} out:fade>
  <div class="header" on:click={() => (isExplain = !isExplain)}>
    <input type="checkbox" bind:checked={todo.isCheck} on:click|stopPropagation />
    <h4>{todo.title}</h4>
  </div>
  {#if isExplain}
    <div class="footer" transition:fade>
      <p>{todo.description}</p>
    </div>
  {/if}
</div>

<style>
  .todo {
    border-radius: 10px;
    width: 300px;
    border: solid #eeeeee 1px;
  }
  .header {
    display: flex;
    align-items: center;
    padding: 10px 20px;
    cursor: pointer;
  }
  .footer {
    padding: 10px 20px;
    text-align: left;
    border-top: solid #eeeeee 1px;
  }
  input {
    margin: auto 0;
    margin-right: 10px;
  }
</style>
