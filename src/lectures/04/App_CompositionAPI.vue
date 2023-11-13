<template>
	<div>
		<h2>반응형 메시지</h2>
		<p>{{ reactiveMessage }}</p>
		<button v-on:click="addReactiveMessage">Add Message</button>
		<h2>일반 메시지</h2>
		<p>{{ normalMessage }}</p>
		<button v-on:click="addNormalMessage">Add Message</button>
	</div>
</template>

<script>
import { isRef, onBeforeMount, onMounted, reactive, ref } from 'vue';

export default {
	setup() {
		// reactive()
		const reactiveMessage = ref('Reactive Message');

		const addReactiveMessage = () => {
			reactiveMessage.value = reactiveMessage.value + '!';
		};
		let normalMessage = 'Normal Message';
		const addNormalMessage = () => {
			normalMessage = normalMessage + '!;';
		};
		console.log('setup');
		onMounted(() => {
			console.log('onMounted');
		});
		onBeforeMount(() => {
			console.log('onBeforeMount');
		});
		return {
			reactiveMessage,
			addReactiveMessage,
			normalMessage,
			addNormalMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
