<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Menu from './components/Menu.vue'
import AdminHome from "./components/AdminHome.vue";
const person = {
  "name":"Delano Oliveira",
  "role":"admin"
}
const isAdmin = person.role === "admin"
</script>

<template>
  <div>
    <Menu />
  </div>
  <HelloWorld v-if="!isAdmin" msg="Olá person.name" />
  <AdminHome v-if="isAdmin"/>
</template>

<style scoped>

</style>
