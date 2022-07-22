<script lang="ts">
  interface ITodo {
    id: number
    isCheck: boolean
    title: string
    description: string
  }

  et todo: ITodo = {
    id: 0,
    isCheck: false,
    title: 'Hello',
    description: 'This is First'
  }
</script>

<!-- TODO: add fade -->
<div class="todo">
  <!-- TODO: click header to explain  -->
  <div class="header">
    <!-- TODO: click checkbox stopPropagation   -->
    <input type="checkbox" />
    <h4>{todo.title}</h4>
  </div>
  <!-- TODO: explain -->
  <div class="footer">
    <p>{todo.description}</p>
  </div>
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
