<template>
	<div>
		<button @click="increment">Counter: {{ counter }}</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		// counter
		const counter = ref(0);
		const increment = () => counter.value++;

		// person
		const person = {};
		const addPerson = () => {};

		return {
			counter,
			increment,
		};
	},
};
</script>

<style lang="scss" scoped></style>
