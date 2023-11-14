<template>
	<div class="card">
		<div v-if="$slots.header" class="card-header">
			<slot name="header" header-message="header 메시지 입니다.">Header</slot>
		</div>
		<div v-if="$slots.default" class="card-body">
			<slot :child-message="childMessage" :hello="'world'" say="안녕하세요"
				>Default Message</slot
			>
		</div>
		<div v-if="$slots.footer" class="card-footer">
			<slot name="footer">Footer</slot>
		</div>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup(props, context) {
		// emit, attrs, slots, expose
		const childMessage = ref('child messsage');
		console.log(context.slots);
		return { childMessage };
	},
};
</script>

<style lang="scss" scoped></style>
