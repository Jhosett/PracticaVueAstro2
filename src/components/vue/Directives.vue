<script setup>
import { ref } from "vue";

const isChecked = ref(true)
const users = ["Pepe", "Ana", "Juana", "Lola"]

</script>

<template>

	<div class="bg-slate-300 p-10 rounded-xl max-w-[500px] m-auto my-[10%]">
		
		<div>
			<input type="checkbox" id="check" v-model="isChecked">
			<label for="check">Pínchame</label>
		</div>

		<div class="bg-blue-400 text-white rounded py-1 px-2 max-w-[150px] my-2 text-center" :class="{'bg-orange-400': isChecked}">
			Este es un mensaje
		</div>

		<div v-if="isChecked">
			Este es un mensaje que podria ocultar
		</div>
		<div v-else>
			Esto se ve porque no cumplio la condiciòn del if
		</div>

		<ul class="my-2 flex gap-2">
			<li v-for="(user, index) in users" :key="index">{{ index }} {{ user }}</li>
		</ul>

	</div>

</template>