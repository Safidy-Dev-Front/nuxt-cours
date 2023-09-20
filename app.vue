<template>
  <div>
    <div>This is the main page</div>
    <div>
      <p>Liste user</p>
      <ul>
        <li v-for="user in users" :key="user.id">
          <p>{{user.name}}</p>
          <p>{{user.username}}</p>
        </li>
      </ul>
    </div>
  </div>
</template>
<script setup>
  const users = ref([])
   asyncData(()=>{
    fetch('https://jsonplaceholder.typicode.com/users')
    .then(res => res.json())
    .then( data => users.value = data)
  })
</script>
