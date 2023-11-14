<template>
	<div class="container py-4">
		Lifecycle
		<input id="input" type="text" value="" />
	</div>
</template>

<script>
import { onBeforeMount, onMounted } from 'vue';

export default {
	beforeCreate() {
		console.log('beforeCreate');
	},
	created() {
		console.log('created');
	},
	setup() {
		console.log('setup');
		// console.log(document.querySelector('#input'));
		// document.querySelector('#input').value = 'helloworld!';
		onBeforeMount(() => {
			console.log('onBeforeMount');
		});
		onMounted(() => {
			console.log('onMounted');
			console.log(document.querySelector('#input'));
			document.querySelector('#input').value = 'helloworld!';
		});
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
