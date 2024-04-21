<script lang="ts">
  import TaskItem from './TaskItem.svelte';

  let tasks: { task: string; taskId: string; }[] = [];
  let newTask: string = '';

  function addTask() {
    if (newTask.trim() !== '') {
      tasks = [...tasks, { task: newTask.trim(), taskId: Date.now().toString() }];
      newTask = '';
    }
  }
</script>

<main>
  <h1>To-Do List</h1>
  <input type="text" bind:value={newTask} placeholder="Enter task name" />
  <button on:click={addTask}>Add Task</button>
  <ul>
    {#each tasks as { task, taskId } (taskId)}
      <TaskItem task={task} taskId={taskId} />
    {/each}
  </ul>
</main>

<style>
  main {
    text-align: center;
    margin-top: 2rem;
  }

  ul {
    margin-top: 2rem;
    list-style-type: none;
    padding: 0;
  }

  h1 {
    color: #FFF;
    font-size: 3rem;
    margin-bottom: 1rem;
  }

  input {
    padding: 0.5rem;
    margin-right: 0.5rem;
    border-radius: 5px;
    border: 1px solid #ccc;
  }

  button {
    padding: 0.5rem;
    border-radius: 5px;
    border: none;
    background-color: #333;
    color: #FFF;
  }
</style>