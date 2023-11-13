<template>
	<div>msg: {{ msg }}</div>
</template>

<script>
export default {
	props: ['msg'],
	setup(props) {
		console.log('props: ', props);
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
