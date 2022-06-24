<template>
    <div class="meun">
        <Tree :data="treeList" @on-click="clickChilden"/>
    </div>
</template>

<script setup lang="ts">
import Tree from "../tree/index.vue"
import { reactive } from "vue"
type TreeList = {
    name: string,
    children?: TreeList[] | []
}
const treeList = reactive<TreeList[]>([
    { name: 'pop1' },
    {
        name: 'pop2',
        children: [{
            name: 'pop2-1'
        }, {
            name: 'pop2-2', children: [{
                name: 'pop2-2-1'
            }]
        }]
    }, {
        name: 'pop3'
    }
])
const clickChilden = (item:TreeList)=>{
    console.log(item)
}
</script>

<style scoped>
.meun {
    width: 1000px;
    border: 1px solid #ccc;
}
</style>
