
<template>
    <div class="tree">
        <div v-for="(item,index) in data" :key="index" @click.stop="clickItem(item)">
            {{item.name}}
            <TreeChild v-if="item.children" :data='item.children' v-on:on-click="clickItem"/>
        </div>
    </div>
</template>

<script setup lang="ts">
import TreeChild from './index.vue'
type TreeList = {
    name: string,
    children?: TreeList[] | []
}
type Props = {
    data?:TreeList[]
}

defineProps<Props>()
const emit = defineEmits(['on-click'])
const clickItem = (item:TreeList)=>{
    emit('on-click',item)
}
</script>

<style scoped>
.tree{
    margin-left: 30px;
    cursor:pointer;
    font-size: 20px;
    text-align: left;
}
</style>
