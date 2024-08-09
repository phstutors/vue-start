<script setup>
const menuItems = ["Home", "About", "Contact", "ASd"]
const person = {
  "name":"Delano Oliveira",
  "role":"admin"
}
const isAdmin = person.role === "admin"
</script>

<template>
  <nav id="menu">
    <ul>
      <li v-for="item in menuItems">
        <a>{{ item }}</a>
      </li>

    </ul>
  </nav>
</template>

<style scoped>
#menu ul { padding:0;
  margin:0;
  background-color:#EDEDED;
  list-style:none;
}

#menu ul li { display: inline; }

#menu ul li a {
  padding: 2px 10px;
  display: inline-block; /* visual do link */
  background-color:#EDEDED;
  color: #333;
  text-decoration: none;
  border-bottom:3px solid #EDEDED;
}

#menu ul li a:hover {
  background-color:#D6D6D6;
  color: #6D6D6D;
  border-bottom:3px solid #EA0000;
}
</style>