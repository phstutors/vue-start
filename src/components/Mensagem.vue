<script setup>
const emit = defineEmits(['close'])
const props = defineProps(["msg","variant"])

function onClose() {
  console.log("message component close")
  emit("close")
}
</script>

<template>
  <div :class="['mensagem',props.variant]">
    <slot></slot>
    <button class="closeButton" @click="onClose()">X</button>
  </div>

</template>

<style scoped>
.mensagem {
  display: flex;
  background: #9e8484;
  justify-content: center;
  align-items: center;
  color: white;
  border-radius: 5px;
}
.danger {
  background: red;
}
.alert {
  background: orange;
}
.success {
  background: green;
}

.closeButton {
  font-size: 5px;
}

</style>