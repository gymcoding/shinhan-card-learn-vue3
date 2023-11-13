<template>
	<div>
		<button v-on:click="increment">Click {{ state.count }}</button>
		<hr />
		<button v-on:click="increment">Click {{ state.deep.count }}</button>
		<hr />
		<p>{{ message }}</p>
		<button v-on:click="addMessage">add messsage</button>
	</div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		const state = reactive({
			count: 0,
			deep: {
				count: 1,
			},
		});
		const increment = () => {
			state.count++;
			state.deep.count++;
		};
		const message = ref('hello world!');
		const addMessage = () => {
			message.value = message.value + '!';
		};
		return {
			state,
			increment,
			message,
			addMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
