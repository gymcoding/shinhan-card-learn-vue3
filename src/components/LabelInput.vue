<template>
	<label>
		<!-- :value="modelValue"
    @input="event => $emit('update:modelValue', event.target.value)" -->
		<input type="text" v-model="model" />
		<button @click="addMessage">click</button>
	</label>
</template>

<script>
import { computed, ref } from 'vue';
export default {
	props: ['modelValue', 'label'],
	emits: ['update:modelValue'],
	setup(props, context) {
		const username = ref('');
		const addMessage = () => {
			context.emit('update:modelValue', props.modelValue + '!');
		};

		const model = computed({
			get: () => props.modelValue,
			set: value => context.emit('update:modelValue', value),
		});

		return { username, addMessage, model };
	},
};
</script>

<style lang="scss" scoped></style>
