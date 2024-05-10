<script setup>

import { ref } from 'vue'

const todos = ref(['Estudiar'])
const todo = ref('')

function add() {
    todos.value.unshift(todo.value)
    todo.value = ''
}
</script>

<template>
    <div class="rounded-xl shadow bg-slate-200 max-w-96 mx-auto mt-12 py-6 px-5">

        <div>

            <input v-model="todo" class="w-4/5 outline-none rounded-l-xl px-5">

            <button @click="add" class="w-1/5 bg-green-600 text-white text-center hover:bg-green-500 rounded-r-xl">
                +
            </button>

        </div>

        <div class="mt-3">

            <div v-for="( todo , index ) in todos" :key="index" class="px-1 bg-orange-300 rounded-lg text-center outline-none mb-2">
                {{ todo }}
            </div>

        </div>

    </div>
</template>