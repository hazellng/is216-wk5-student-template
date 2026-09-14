<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])
const newItem = ref('')
// TODO: Add Code Here
function deleteItem(index) {
    items.value.splice(index, 1)
}

function add() {
    items.value.push(newItem.value)
    newItem.value = ''
}

</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul >
        <li v-for="(item, index) in items">{{ item }}
            <button @click="deleteItem(index)">Delete!</button>
            <!-- <button @click="items.splice(index,1)">Delete!</button> -->
        </li>
    </ul> 

    <input type="text" v-model="newItem" @keyup.enter="items.push(newItem)">
    <button @click="add()">Add!</button>
    <!-- <button @click="items.push(newItem)" >Add!</button> -->
 
   
</template>
