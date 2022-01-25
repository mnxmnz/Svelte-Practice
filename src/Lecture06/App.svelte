<script>
  import { writable } from 'svelte/store';
  import Todo from './Todo.svelte';

  let todos = writable([]);
  let id = 1;
  let task = '';

  function createTodo() {
    if (!task.trim()) {
      task = '';
      return;
    }

    $todos.push({ id, task });
    $todos = $todos;
    id += 1;
    task = '';
  }
</script>

<main>
  <h1>Simple To Do List</h1>
</main>

<div class="text-input">
  <input type="text" bind:value={task} on:keydown={e => e.key === 'Enter' && createTodo()} />
  <button on:click={createTodo}>Create To Do</button>
</div>

<div>
  {#each $todos as todo}
    <Todo {todos} {todo} />
  {/each}
</div>
