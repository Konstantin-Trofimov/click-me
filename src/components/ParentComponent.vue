<template>
  <ChildComponent :count="count" @click="updateCounter"/>
</template>

<script setup>
import { ref } from 'vue'
import ChildComponent from './ChildComponent.vue'

const count = ref(0)
const updateCounter = () => {
  count.value++
}
</script>