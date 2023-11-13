<template>
	<div></div>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
	setup() {
		const count = ref(0);
		const state = reactive({
			count,
		});
		count.value++;
		console.log(count.value); // 1
		console.log(state.count); // 1

		const books = reactive([ref('Vue 3 Guide')]);
		// need .value here
		console.log(books[0].value);
	},
};
</script>

<style lang="scss" scoped></style>
