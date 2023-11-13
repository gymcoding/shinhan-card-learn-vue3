<template>
	<div>
		<div class="text" :class="{ 'text-danger': isActive, active: true }">
			텍스트입니다.
		</div>
		<div class="text" :class="[classObject, 'text-weight-200']">
			텍스트입니다.
		</div>
		<button v-on:click="toggleActive">toggle active</button>
	</div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
	setup() {
		const isActive = ref(true);
		const classObject = computed(() => {
			return { 'text-danger': isActive.value, active: true };
		});

		const toggleActive = () => {
			isActive.value = !isActive.value;
		};
		return {
			isActive,
			toggleActive,
			classObject,
		};
	},
};
</script>

<style scoped>
.text-danger {
	color: red;
}
.active {
	font-weight: 900;
}
</style>
