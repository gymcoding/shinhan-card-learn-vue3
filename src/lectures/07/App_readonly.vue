<template>
	<div></div>
</template>

<script>
import { reactive, readonly } from 'vue';

export default {
	setup() {
		const original = reactive({
			count: 0,
		});
		original.count++;

		const copy = readonly(original);
		copy.count++;
		// console.log('original.count: ', original.count);
		console.log('copy.count: ', copy.count);

		return {
			original,
		};
	},
};
</script>

<style lang="scss" scoped></style>
