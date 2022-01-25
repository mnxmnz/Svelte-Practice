<script>
  export let todos;
  export let todo;

  let isEdit = false;
  let task = '';

  function onEdit() {
    isEdit = true;
    task = todo.task;
  }

  function offEdit() {
    isEdit = false;
  }

  function updateTodo() {
    todo.task = task;
    offEdit();
  }

  function deleteTodo() {
    $todos = $todos.filter(t => t.id !== todo.id);
  }
</script>

{#if isEdit}
  <div>
    <input type="text" bind:value={task} on:keydown={e => e.key === 'Enter' && updateTodo()} />
    <button on:click={updateTodo}>OK</button>
    <button on:click={offEdit}>Cancel</button>
  </div>
{:else}
  <div>
    <span>{todo.task}</span>
    <button on:click={onEdit}>Edit</button>
    <button on:click={deleteTodo}>Delete</button>
  </div>
{/if}

<style>
  div {
    margin: 10px 0;
  }
</style>
