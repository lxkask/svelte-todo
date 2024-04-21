<script lang="ts">
  export let task: string;
  export let taskId: string;
</script>

<li>{task}</li>

<style>
  li {
    padding: 0.5rem;
    margin-top: 1rem;
    border-radius: 5px;
    background-color: #f4f4f4;
    text-align: left;
  }
</style>