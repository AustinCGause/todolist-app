<template>
  <h1 class="text-3xl font-bold">
    Hello Mom!
  </h1>underline
</template>

<script>
  fetch('/api/tasks')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error: ', error));
</script>