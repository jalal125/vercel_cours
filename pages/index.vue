<script setup>
const { $supabase } = useNuxtApp()
const { data } = await $supabase.from('users').select('*')
</script>

<template>
  <div>
    <h1>Liste des utilisateurs</h1>
    <ul>
      <li v-for="user in data" :key="user.id">
        {{ user.name }}
      </li>
    </ul>
  </div>
</template>
