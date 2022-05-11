<script setup lang="ts">
const props = withDefaults(
  defineProps<{
    msg?:string,
    ageList:Array<number>
  }>(),
    {msg:'hello',
    ageList:()=>[1,2]
    }
)
</script>

<template>
  <h1>{{ msg }}</h1>
  <h1>{{ ageList }}</h1>
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
