<template>
	<label>
		{{ label }}
		<input type="text" v-model="model" v-bind="$attrs" />
	</label>
</template>

<script>
import { computed, ref } from 'vue';
export default {
	props: ['modelValue', 'label'],
	emits: ['update:modelValue'],
	// inheritAttrs: false,
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
