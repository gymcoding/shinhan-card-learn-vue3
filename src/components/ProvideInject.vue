<template>
	<div class="container py-4">
		<div class="card">
			<div class="card-header">ProvideInject</div>
			<div class="card-body">
				<button @click="counter++">counter: {{ counter }}</button>
				<ProvideInjectChild></ProvideInjectChild>
			</div>
		</div>
	</div>
</template>

<script>
import { provide, readonly, ref } from 'vue';
import ProvideInjectChild from './ProvideInjectChild.vue';
export default {
	components: {
		ProvideInjectChild,
	},
	setup() {
		const counter = ref(0);
		const incrementCount = () => counter.value++;
		provide('counter', readonly(counter));
		provide('incrementCount', incrementCount);

		return {
			counter,
		};
	},
};
</script>

<style lang="scss" scoped></style>
