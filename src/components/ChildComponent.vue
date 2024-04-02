<template>
  <div>
    <button
      v-if="count === deep"
      @click="emit('click')"
    >
      click me
    </button>
    <ChildComponent
      v-else 
      :deep="deep + 1" 
      :count="count"
      @click="emit('click')"
    />
  </div>
</template>

<script setup>
const props = defineProps({
  count: { type: Number, required: true },
  deep: { type: Number, default: 0 },
})
const emit = defineEmits(['click'])
</script>

<style scoped>
  div {
    border: 1px solid red;
    width: 95%;
    height: 95%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
