<script setup>
import { ref } from 'vue';

const show = ref(true);
const list = ref([1, 2, 3]);
</script>

<template>
    <div class="container">
        <div class="buttons">
            <button @click="show = !show">Toggle List</button>
            <button @click="list.push(list.length + 1)">Push Number</button>
            <button @click="list.pop()">Pop Number</button>
            <button @click="list.reverse()">Reverse List</button>
        </div>

        <div class="list-container">
            <ul v-if="show && list.length" class="list">
                <li v-for="item in list" :key="item" class="list-item">{{ item }}</li>
            </ul>
            <p v-else-if="list.length" class="message">List is not empty, but hidden.</p>
            <p v-else class="message">List is empty.</p>
        </div>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background-color: #f0f4f8;
    font-family: Arial, sans-serif;
    padding: 20px;
    box-sizing: border-box;
}

.buttons {
    margin-bottom: 20px;
}

button {
    margin: 5px;
    padding: 10px 20px;
    font-size: 1rem;
    color: white;
    background-color: #007BFF;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #0056b3;
}

.list-container {
    text-align: center;
}

.list {
    list-style-type: none;
    padding: 0;
}

.list-item {
    padding: 10px;
    margin: 5px 0;
    background-color: #ffffff;
    border: 1px solid #dddddd;
    border-radius: 5px;
    color: #333333;
    font-size: 1.2rem;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.message {
    font-size: 1.2rem;
    color: #555555;
    margin-top: 10px;
}
</style>
