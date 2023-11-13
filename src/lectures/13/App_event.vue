<template>
	<div>
		<button v-on:click="printEventInfo('파라미터', $event)">
			inline event handler
		</button>
	</div>
</template>

<script>
export default {
	setup() {
		const printEventInfo = (params, event) => {
			console.log('params: ', params);
			console.log('event: ', event);
			//
		};
		return { printEventInfo };
	},
};
</script>

<style lang="scss" scoped></style>
