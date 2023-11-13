<template>
	<div>
		<button v-on:click="increment">Counter: {{ count }}</button>
	</div>
</template>

<script>
export default {
	data: () => {
		return {
			count: 0,
			person: {},
			animal: {},
		};
	},
	methods: {
		increment() {
			this.count++;
		},
		addPerson() {},
	},
};
</script>

<style scoped></style>
