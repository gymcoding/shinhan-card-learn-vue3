<template>
	<div>
		<form>
			<LabelInput
				:model-value="firstname"
				@update:model-value="value => $emit('update:firstname', value)"
			/>
			<LabelInput
				:model-value="lastname"
				@update:model-value="value => $emit('update:lastname', value)"
			/>
		</form>
	</div>
</template>

<script>
import LabelInput from './LabelInput.vue';
export default {
	components: {
		LabelInput,
	},
	props: ['firstname', 'lastname'],
	emits: ['update:firstname', 'update:lastnamee'],
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
