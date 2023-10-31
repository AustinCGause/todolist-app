<template>
  <h1 class="text-3xl font-bold">
    Hello Mom!
  </h1>
  <ul id="task-list">

  </ul>
</template>

<script>
  import Navigation from 'components/'

  fetch('/api/tasks')
    .then(response => {
      if (!response.ok) {
        throw new Error('HTTP error! Status: ${response.status}');
      }
      return response.json();
    })
    .then(data => {
      const taskListElement = document.getElementById('task-list');
      data.tasks.forEach(task => {
        const li = document.createElement('li');
        li.textContent = task.title;
        taskListElement.appendChild(li);
      });
    })
    .catch(error => console.error('Error: ', error));
</script>