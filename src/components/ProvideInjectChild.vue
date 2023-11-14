<template>
	<div class="card">
		<div class="card-header">Child Component</div>
		<div class="card-body">
			<ProvideInjectDeepChild />
		</div>
	</div>
</template>

<script>
import ProvideInjectDeepChild from './ProvideInjectDeepChild.vue';
export default {
	components: {
		ProvideInjectDeepChild,
	},
};
</script>

<style lang="scss" scoped></style>
