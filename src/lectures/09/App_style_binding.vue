<template>
	<div>
		<div :style="styleObject">
			Lorem ipsum dolor, sit amet consectetur adipisicing elit. Similique neque
			quam recusandae a veniam quae possimus esse et, ab quis eius quisquam!
			Aperiam dolor rerum totam libero perspiciatis, fuga odit.
		</div>
		<button v-on:click="fontSize--">-</button>
		<button v-on:click="fontSize++">+</button>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		// const styleObject = reactive({
		// 	color: 'red',
		// 	fontSize: '13px',
		// });

		const fontSize = ref(13);

		const styleObject = computed(() => ({
			color: 'red',
			fontSize: fontSize.value + 'px',
		}));

		return {
			styleObject,
			fontSize,
		};
	},
};
</script>

<style lang="scss" scoped></style>
