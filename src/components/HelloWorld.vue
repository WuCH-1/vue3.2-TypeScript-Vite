<script setup lang="ts">
import DefineProps from 'com/DefineProps.vue'
import { ref, reactive, computed } from 'vue'
    let count = ref(0)
    const obj = reactive({
      a:1,
      b:3
    })
    const sum = computed(()=>{
      return count.value + obj.b
    })
</script>

<template>
  <h1>{{ count }}</h1>
  <div>{{ obj.b }}</div>
  <div>{{ sum }}</div>
  <DefineProps msg="Hello Vue 3 + TypeScript + Vite" />
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
