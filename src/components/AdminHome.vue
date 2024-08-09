<script setup>
import {ref, reactive, onMounted} from 'vue'
import Mensagem from "./Mensagem.vue";
const person = ref({
  "name":"Delano Oliveira",
  "role":"admin"
})
const users = [
  {"name": "João", "role":"admin"},
  {"name": "Marcos", "role":"user"},
  {"name": "Gabrielly", "role":"user"},
]

var todos = reactive([])

async function getTodos() {
  const response = await fetch("https://jsonplaceholder.typicode.com/todos")
  todos = await response.json()
  console.log(todos)
}


var message = reactive(
    {active: false, variant:"success", text:""}
);

onMounted(() =>
    getTodos()
)


function pressAlterar() {
  console.log("Chamou alterar")
  message.active = true
  message.texto = "Seu nome foi alterado para " + this.person.name

}

function closeMessage() {
  console.log("closeMessage")
  message.active = false
}



</script>

<template>
  <Mensagem v-if="message.active" :variant="message.variant" @close="closeMessage()">
    {{message.texto}}
  </Mensagem>
  <label id="label">Altere seu nome</label><input v-model="person.name">
  <button @click="getTodos()">Alterar</button>

  <h2>Todos</h2>
  <ul>
    <li v-for="item in todos">{{item.title}}</li>
  </ul>


</template>

<style scoped>

</style>