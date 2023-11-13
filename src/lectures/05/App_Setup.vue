<template>
	<div>
		<p>{{ counter }}</p>
		<p>{{ message }}</p>
		<TestComp v-bind:msg="'msg 입니다'"></TestComp>
	</div>
</template>

<script>
import { ref } from 'vue';
import TestComp from './lectures/04/TestComp.vue';

export default {
	components: {
		TestComp,
	},
	setup(props, context) {
		const counter = ref(0);
		const message = ref('Hello Vue3');
		return {
			counter,
			message,
		};
	},
};
</script>

<style lang="scss" scoped></style>
