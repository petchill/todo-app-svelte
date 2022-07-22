<script lang="ts">
  import Modal from './components/Modal.svelte'
  import TodoList from './components/TodoList.svelte'
  import type { ITodo } from './type'
  export let title: string = 'Svelte'

  let isShowHandsomeModal = false

  let todoList: ITodo[] = [
    {
      id: 1,
      isCheck: false,
      title: 'Hello First',
      description: 'this is the first todo card'
    },
    {
      id: 2,
      isCheck: true,
      title: 'Hello second',
      description: 'this is the first todo card'
    }
  ]
</script>

<Modal bind:isShow={isShowHandsomeModal}>
  <h3 slot="subtitle">The Most Handsome guy is</h3>
  <h1 slot="title">Prayut Chan-O-Cha !!!!</h1>
</Modal>
<main>
  <h1>Hello {title}!</h1>
  <button on:click={() => (isShowHandsomeModal = !isShowHandsomeModal)}>Show Modal</button>
  <TodoList bind:todoList />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
